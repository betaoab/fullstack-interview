# Problem A: The Overflowing Folder

You are working on a Django application, hosted on a virtual cloud server (e.g. an instance on Amazon EC2 or Google Cloud, a droplet on Digital Ocean, an Heroku Dyno...).

Your application collects documents and saves them in the folder `/media/documents`. That folder is located directly on the file system of your virtual server. 

The documents you are handling are small binary files (pdf-like), with a size ranging between 2Mb and 10Mb. 

A (very summarized) codebase can be found just below.

```python
from django import models
from django.core.files.storage import FileSystemStorage

fs = FileSystemStorage(location='/media/documents')

class Document(models.Model):
    title = models.CharField(max_length=200)
    document = models.FileField(storage=fs)
    # ...
```

After a few years of operations, and after having collected 2 terabytes of documents, you realize that you are running out of storage on your instance. Your task is to find a way to keep your service up and running, without losing any data in the process.

For some reason, you are unable to add block storage or scale the file system capacity of your virtual server. You can consider your instance "locked". On the other hand, you still have access to all other services provided by your cloud host, and have access to reasonable budget if needs be.

Can you think of a few ways to get yourself out of this situation, and what would be the best course of action you recommend? 

You can illustrate your solution with diagrams, commands, code or pseudocode, if you need.

# Problem B: Old MacDonald, E-I-E-I-O

You are supporting a library that prints the lyrics of a very famous children's song to the console (`nursery.js`).

Your business is doing well, and your customer now wants your library to be able to generate different versions of the song (with a similar structure), but with an arbitrary set of animals and sounds. 

The customer also insists on being able to configure if Old MacDonald is a lady or a gentleman (and whether or not the animals are on "his" or "her" farm). 

The customer does not know yet which animals will get added to the farm, and he doesn't know how many there will be either.  

The final deliverable should be javascript (ES6+) code that takes any arguments of your choosing and prints the complete song.

The customer would also be very interested in seeing a working unit test that validates that indeed, Old MacDonald has all the animals on his farm and that they sound proper.

# Submission
Please send your completed work as a .zip to solen@betao.se.
