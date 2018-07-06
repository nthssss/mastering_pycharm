Debugging workflow
---
A friend of mine, who used Java in his day job, sent me a code snippet that he
needed help with. He was new to Python and was still getting used to the differences
between Java and Python. He mostly worked with databases, so he was exploring
the different ORMs that were available. He tried SQLAlchemy, the Django ORM, and
eventually, found that he liked a still very new ORM called Pony. At that time, the
documentation for Pony was still in its infancy, so he sent me the code so that I could
help him out. It looked similar to this:
```python
__author__ = "John Doe"
import string
import random
from pony.orm import db_session, commit, Database, Required
db = Database()
class Person(db.Entity):
    name = Required(str)
    age = Required(int)
vowels = 'aeiou'
consonants = str(letter for letter in string.ascii_lowercase if letter
not in vowels)
def gen():
    return random.choice(consonants) + random.choice(vowels)
names = [(gen() for _ in range(random.randint(3, 4))) for i in
range(100)]
db.bind('sqlite', 'data.sqlite', create_db=True)
db.generate_mapping(create_tables=True)
with db_session:
    for name in names:
        Person(name=name, age=random.randint(5, 21))
commit()
```