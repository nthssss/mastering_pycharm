Processes
---
Processes are handled similarly in PyCharm. We will make only a small change to
the preceding code—importing  _Process_ instead of  _Thread _and starting  _Process_ instead of  _Thread_ :


```python
# encoding=utf-8
from multiprocessing import Process
import requests
def download(url):
response = requests.get(url)
if response.status_code == 200:
print "Success -> {:<75} | Length -> {}".format(response.url,
len(response.content))
else:
print "Failure -> {:>75}".format(response.url)
if __name__ == '__main__':
urls = "http://www.google.com http://www.bing.com http://www.
yahoo.com http://news.ycombinator.com".split()
for u in urls:
Process(target=download, args=(u,)).start()
```
If we try to debug this by setting the breakpoint at the same place, we get process IDs
instead of thread numbers since we're creating processes.
