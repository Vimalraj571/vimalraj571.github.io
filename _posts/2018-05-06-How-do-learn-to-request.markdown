---
title: "How Do i Learn to request"
layout: post
permalink: "/How-Do-i-Learn-to-request.html"
tags: [python, request , query string]
---

Hi Today i came across the situation to make the query string on server (May likely to the API endpoint)
And get the response show it on terminal

Query String
------------

Query String is the process like give the string in url and get the response

Like google simple query string using the url 

It is the very basic query string using Google

- https://www.google.com/search?q=python+things


Code
----

I done that by using python 3.5! Using the library module called urllib.
Using the urlretrieve function you can make the Query string to the server
But the major disappoint is you can't get the response directly 
the difficulty is get the response as the txt file
open using the file.open() kind a things

So using the urlretrieve library function the we can make request easily but 
the response is difficult to get and see in terminal  (in my case)

Be i didn't used any of the magic things so i tried the library function urlretrieve how i turned down that

{% highlight python %}

from urllib.request import urlretrieve
from urllib.parse import urlencode

d = {'q' : 'This simple sentence contain shots of words' }
qs = urlencode(d)	
connection = urlretrieve("http://www.wdylike.appspot.com/?"+qs) #Or pass second argument as txt.txt get in same dir
print(connection)


{% endhighlight %}

qs = urlencode(d) gives the query string as like 

http://www.wdylike.appspot.com/?q=This+simple+sentence+contain+shots+of+words (Pretty cool right)


- RESPONSE at : ('/tmp/tmpl56ujjzh', <http.client.HTTPMessage object at 0x7fea196748d0>)

In this case again i have to read the tmpl56ujjzh.txt file using open.file() and get the response


The Magic
---------

The Magic thing is called request

which is available in PyPy you can use install it using the 

- pip install request

When you have anaconda it is preinstalled  

Now i make the request and response with the hesitation Now the code will be like

{% highlight python %}

import requests

dic = {'q' : file_content }
URL = 'http://www.wdylike.appspot.com' 
r = requests.get(url= URL,params= dic)
print(r.text)

{% endhighlight %}

- REPONSE as : false

I can simply put r.text or r.json() to show the response

the simple dic will converted as the Query string like this:

- http://www.wdylike.appspot.com/?q=This+simple+sentence+contain+shots+of+words

using the request package

Thanks to the Kennith Ritz 
- PS: Creater of request

- 1.Things i learned make sure have the pypy packages to easy the work
- 2.How to do code on Google Style guide
- 3.As well as as how to request 


Happy coding !! :)