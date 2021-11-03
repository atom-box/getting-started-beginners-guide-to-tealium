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

More of these questions can be answered by putting a little Javascript into your page with JS listeners. That code can do AJAX calls that send a JS object as a POST to somewhere. A common place to send this HTTPS POST is your account at Google Analytics. Here are [a half dozen examples](https://tatll.me/posts/tracking-pixels-and-analytics/) of real web pages calling the JS script. When the JS file loads it instantiates a data object, it stores a few dozen properties on the object, POSTs that object to a server of your choosing, and then, sets 0 or more listeners that get triggered when users do various things. The list of things that can be listened for are pretty much synonymous with the many things JS can listen for, hover on a certain id, button clicks, scrolling.  All of these can be set as properties on the mono object and that object can be sent in as a POST. (TODO Get this reviewed by someone more senior than me!).

## Tealium IQ

Tealium is a SaaS company. One of their products is the *Tealium IQ Tag Management System*. This solves the problem of how to send data to multiple places. Sites that are trying to get a lot of data from their visitor experiences usually send their data to more than one analyzer. The problem: each data send would require its own JS snippet to send an object. That's bad for performance and it is hard to maintain. Tealium makes a GUI for managing tags and it allows sites to put in *just a single tag*. The single tag then reports back to the GUI. 

The tag can be added all over in your site's ecosystem, including on its app. And the [Tealium docs](https://tealium.com/integrations/) have pre-written code for writing the tag in the syntax of plain JS, Wordpress, AppleTV, Roku, iOS, Drupal, Shopify.  Tealium's single tag works with Ionic too, if you [add a wrapper](https://pikl.us/zuwwyw86) around the Tealium Cordova plug-in.

Once the __single tag__ is added, the user can open the Tealium GUI and configure the data to go to many places, and the variables will get re-named automatically. For example, if folks in your team are using RocketFuel and Adobe Analytics *and* Twitter Analytics, if you were coding a purchase id by hand, you would have to save it as transid and s.purchase_id AND pid. Hassle! And error prone. But by using Tealium, the Tealium devs keep all of those __variable name configurations__ up to date. Way more efficient. See more at the [Tealium dev docs](https://docs.tealium.com/platforms/getting-started-web/data-layer/an-introduction-to-the-data-layer/)

Tealium claims [eight major benefits](https://tealium.com/products/tealium-iq-tag-management-system/) to doing the tagging with Tealium. For example, having easier centralized tag and data configuration makes GDPR and privacy compliance more workable. Also the Tealium CDN is fast, which helps performance. The ROI can be large. One [testimonial](https://youtu.be/T-fYBndhEpo) from Intrepid adventure travel described the ROI goal as being 1.20x and the actual ROI turned out to be more like 10x.

## Sending data to more than one place

After placing a single data tag and forwarding the data to Tealium, marketing folks can go into the GUI and forward that data flow into [hundreds(!) of places](https://tealium.com/integrations/).  Just some: LinkedIn Insights, Adobe App Measurement, Mailchimp, Twilio, AWS Redshift, Facebook Conversions, Hubspot, et al.

## Competitors

Wikipedia lists [six tag managers](https://en.wikipedia.org/wiki/Tag_management_system)

    Adobe  
    Ensighten  
    Google (Google Tag Manager)  
    Matomo (opensource)  
    Signal  
    Tealium  
    Yahoo  

## Getting started links

* [Web](https://docs.tealium.com/platforms/getting-started-web/)
* [Mobile](https://docs.tealium.com/platforms/getting-started/)
* [Tealium's API](https://docs.tealium.com/platforms/getting-started/)

## Learning TIQ

https://community.tealiumiq.com/t5/iQ-Tag-Management/Tag-Management-Concepts/ta-p/15883  
https://community.tealiumiq.com/t5/JavaScript-utag-js/Event-Tracking/ta-p/15588  
https://community.tealiumiq.com/t5/Tags/SERIES-Google-Universal-Analytics-Guide-for-iQ-Tag-Management/ta-p/9494  

## Learning AudienceStream

https://community.tealiumiq.com/t5/Universal-Data-Hub/Tealium-Collect-Tag-Setup-Guide/ta-p/11923  
https://community.tealiumiq.com/t5/Universal-Data-Hub/Introduction-to-AudienceStream/ta-p/16087  
https://community.tealiumiq.com/t5/Universal-Data-Hub/Using-Attributes/ta-p/11926  
https://community.tealiumiq.com/t5/Universal-Data-Hub/Using-Enrichments/ta-p/11932  

## The weird fake ecommerce store is here

https://ecommerce.tealiumdemo.com/training

## Left off in videos here:
* 12%
* https://education.tealium.com/learn/course/en-as-bsc-elrn/audiencestream-overview/audiencestream-overview?page=3

## Next Action
* Try signing in to that fake ecommerce dashboard they gave you access to. Does it have data? Can you do what the guy in the above video did?


## Getting started with Google Analytics 4  
 
From [Kayle Larkin](https://ahrefs.com/blog/how-to-use-google-analytics/).  Go to [analytics.google.com](http://analytics.google.com).  

    Click Start measuring.
    Enter an account name (This is for internal purposes. We recommend using your company name.)
    Edit data sharing settings (optional).
    Click Next.
    Enter a property name(This is for internal use only and your website domain works well, especially if working with multiple websites under one company.)
    Check the reporting time zone and currency (This should be accurate for the business’s location).
    
    I did not do this:
    Click Show advanced options.
    Toggle the option to ‘Create a University Analytics property’ on (This is considered best practice to keep GA4 enhanced measures enabled.)
    Enter Website URL.
    Click Next.

    I did not do this:
    Enter industry and business size information (optional).
    Click Create.
    Accept the Google Analytics Terms of Service Agreement (Be sure to familiarize yourself with this before agreeing, as there may be specific privacy rules and regulations for your location.)
    Check web stream details (Ensure everything is correct, including things like HTTP vs. HTTPS and www vs. non-www. These may skew data accuracy.)

## In GA4

To get the mini dashboard modal, click top left tab "All accounts > evan-genest > pikl-us" That will get you a smaller dashboard featuring
1. analytics accounts
2. tag manager
3. optimizer
4. data studio


