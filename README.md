# *Total* Beginners Guide to Using Tealium

## Intro

__Web analytics__, generally, can answer these questions: How many visitors does your site get? What do they do while they are there? Who is visiting your site? What can you know about an anonymous visitor, from the moment they land on your homepage, even though they are anonymous?

A few of these questions could be answered by looking at your logs:

```bash
evan@nodejs-nyc:~$ sudo tail -n 300 /var/log/apache2/access.log | grep pikl | wc
     10     211    2189
evan@nodejs-nyc:~$ sudo tail -n 300 /var/log/apache2/access.log | grep tatll | wc
      8     175    1980
```

More of these questions can be answered by putting a little Javascript into your page with JS listeners. That code can do AJAX calls that send a JS object as a POST to somewhere. A common place to send this HTTPS POST is your account at Google Analytics. 

## Tealium products

Tealium is a SaaS company. One of their products is the *Tealium IQ Tag Management System*. This solves the problem of how to send data to multiple places. Sites that are trying to get a lot of data from their visitor experiences usually send their data to more than one analyzer. The problem: each data send would require its own JS snippet to send an object. That's bad for performance and it is hard to maintain. Tealium makes a GUI for managing tags and it allows sites to still put in just a single tag. The tag then reports back to the GUI. 
