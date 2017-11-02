---
layout: post
title: Bloc Jams Case Study
permalink: /portfolio/blocjams
feature-img: "img/color.png"
hide: true
---
##Explanation
Bloc Jams is a music app project that helped me learn both JQuery and AngularJS. While the app was able to play a basic album in the JQuery version, I wanted to create a more scalable app that could hold multiple albums and tracks. Also, the flexibility of AngularJS allowed me to keep my code base smaller while making it easier to read.

##Problem
The JQuery Version of Bloc Jams was a single, one-dimensional page that showed one album.

{:.center}
![]({{ site.baseurl }}/img/bloc-jams-jquery1.jpg)

Right away, it seemed as though having multiple pages such as a page to show and store albums, a home page, and any additional layers like a blog would be difficult since items like the player bar would need to be carried over on each page. Instead of having all of the extra code, it made the most sense to go with a more scalable approach and use AngularJS to build a single page app that could use more bite-sized chunks of code.

##Solution & Results
Moving over to AngularJS helped to minimize the need for duplicate code on HTML pages. Take for example the player bar HTML for JQuery version of Bloc Jams:

{% highlight HTML %}
<!-- Player Bar  -->
<section id="player-bar">
  <section id="buttons">
    <!-- Previous Button -->
    <button id="previous">
      <span class="ion-skip-backward"></span>
    </button>
    <!-- Play Button  -->
    <button id="play-pause">
      <span class="ion-play"></span>
      <span class="ion-pause"></span>
    </button>
    <!-- Next Button -->
    <button id="next">
      <span class="ion-skip-forward"></span>
    </button>
  </section>
  <!-- Time Control  -->
  <section id="time-control">
    <div class="current-time">–:––</div>
    <input type="range" class="seek-bar" value="0">
    <div class="total-time">–:––</div>
  </section>
  <!-- Volume Control  -->
  <div id="volume-control">
    <div class="icon ion-volume-low"></div>
    <input type="range" class="seek-bar" value="80">
    <div class="icon ion-volume-high"></div>
  </div>
{% endhighlight %}

We would need to add this to each page that we created. However, with AngularJS, we are able to house this in it's own file and call it onto whichever page we want with a single line of code. Not only does this allow for less duplication of code, but it keeps the amount of code on each HTML file much smaller and easier to manage. In the AngularJS version of Bloc Jams, we can easily use ngInclude on whichever template we need to and call in the player bar:

{% hightlight HTML %}
<ng-include src="'/templates/player_bar.html'"></ng-include>
{% endhighlight %}

##Results

The end result was a much more scalable, single page app that had more flexibility when it came to have multiple albums and a more dynamic player bar. The code base was also broken out in a way that it was easy to understand which service was doing what and created bite sized code that was easier to troubleshoot while building. And, it was much more appealing to the eyes too!

{:.center}
![]({{ site.baseurl }}/img/bloc-jams-2.jpg)

##Conclusion

Both versions of Bloc Jams have their strengths and weaknesses, but for app scalability, AngularJS wins out. For me, having smaller pieces of code to work with was much easier for me. I also like that I can easily add pages and pull in code I need without having to repurpose certain things, like a player bar, on every page. Very happy I was able to work with both, but Angular is the clear winner for me!
