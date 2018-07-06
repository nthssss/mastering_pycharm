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
I ran this fine in debug mode, and got an exception in the console, saying that it was
a  MappingError , so I looked at the file and found out that the script did not bind to
a database before generating mappings, so that was easy enough to fix— it needed
to bind before generating mappings. But then came another problem, and that
was  _TypeError_ :
![](/assets/0609.png)
So, it's saying that we have  TypeError , and that it was expecting Unicode, but for
what? This is where frames come in handy. Frames, located on the left-hand side
of the debug menu, are like layers in an application. Frames showcase this callback
sequence (or a function call stack), letting you jump between the files where the
problem was caused.
![](/assets/0610.png)
