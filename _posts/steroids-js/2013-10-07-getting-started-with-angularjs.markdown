---
layout: post
title:  "Getting Started with AngularJS"
date:   2013-10-07 22:51:34
categories: steroids-js
platforms: iOS, Android
---

This guides explains how to get started with the JavaScript framework AngularJS while using Steroids.

## Setup

The easiest way to get started with AngularJS on Stroids is to take advantage of the 'steroids generate' command. First create a new Steroids project. After going to your project directory, run:

{% highlight bash %}
$ steroids generate ng-resource <resourceName>
{% endhighlight %}
 
which creates an AngularJS boilerplate for you.

However, if you now run '$ steroids connect' and 'simulator', instead of the sample AngularJS app residing in 'app/' folder, you will see the 'www/index.html' file. Localhost is to help here. Your WebViews will be served by the device's web server while using AngularJS. Open 'config/application.coffee' and change the app's intial location to point to your resource's index view:

{% highlight coffeescript %}
steroids.config.location = "http://localhost/views/<resourceName>/index.html"
{% endhighlight %}

Now, after '$ steroids connect' and 'simulator' or hitting enter if already connected, you can see the sample AngularJS app, on top of which you can build your own AngularJS magic.

Inside the 'app/' folder, 'app/controllers/ is the place for your AngularJS controllers and 'app/models/ the place for your AngularJS services. For the views, declare your dependencies in 'app/views/layouts/<resourceName>.html. The partial templates that extend this layout template go to the app/views/<resourceName>/ folder. 

## Local data files, images and stylesheets

If you are using local data, your data files go to the 'www/' folder of the Steroids project. For example, if your Restangular baseUrl is set to 'http://localhost/data', you data files go to the 'www/data/' folder. The same applies to image files. For example:

{% highlight html %}
<img src="/images/my_image.png">
{% endhighlight %}

points to 'my_image.png' in the 'www/images/' folder. The stylesheets folder is also located in the 'www/' folder.

Happy building!



