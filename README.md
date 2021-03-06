## Website Performance Optimization portfolio project

Your challenge, if you wish to accept it (and we sure hope you will), is to optimize this online portfolio for speed! In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

To get started, check out the repository, inspect the code,

### Getting started

####Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ngrok 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!

####Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js. 

You might find the FPS Counter/HUD Display useful in Chrome developer tools described here: [Chrome Dev Tools tips-and-tricks](https://developer.chrome.com/devtools/docs/tips-and-tricks).

### Optimization Tips and Tricks
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">The fewer the downloads, the better</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">Reduce the size of text</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">Optimize images</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP caching</a>

### Customization with Bootstrap
The portfolio was built on Twitter's <a href="http://getbootstrap.com/">Bootstrap</a> framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>

### Sample Portfolios

Feeling uninspired by the portfolio? Here's a list of cool portfolios I found after a few minutes of Googling.

* <a href="http://www.reddit.com/r/webdev/comments/280qkr/would_anybody_like_to_post_their_portfolio_site/">A great discussion about portfolios on reddit</a>
* <a href="http://ianlunn.co.uk/">http://ianlunn.co.uk/</a>
* <a href="http://www.adhamdannaway.com/portfolio">http://www.adhamdannaway.com/portfolio</a>
* <a href="http://www.timboelaars.nl/">http://www.timboelaars.nl/</a>
* <a href="http://futoryan.prosite.com/">http://futoryan.prosite.com/</a>
* <a href="http://playonpixels.prosite.com/21591/projects">http://playonpixels.prosite.com/21591/projects</a>
* <a href="http://colintrenter.prosite.com/">http://colintrenter.prosite.com/</a>
* <a href="http://calebmorris.prosite.com/">http://calebmorris.prosite.com/</a>
* <a href="http://www.cullywright.com/">http://www.cullywright.com/</a>
* <a href="http://yourjustlucky.com/">http://yourjustlucky.com/</a>
* <a href="http://nicoledominguez.com/portfolio/">http://nicoledominguez.com/portfolio/</a>
* <a href="http://www.roxannecook.com/">http://www.roxannecook.com/</a>
* <a href="http://www.84colors.com/portfolio.html">http://www.84colors.com/portfolio.html</a>

**** VSG NOTES ****
Changes made to the project in order to increase speed, performance and user interaction:

Modifications to Web_Optimization_Gidenko-_4 Img and views images folders: 
	1. In order to improve speed index score I downloaded gulp and optimized images using gulp task manager.

Modification to Index.html to get PageSpeed Insights performance improvement:
	1. Disabled links and inlined code from style.css and print.css.
	2. Disabled font imports.
	3. Compressed and images by using ImageOptim and 'gulp-responsive-images'
	4. Copied and commpressed image 'pizzeria.jpeg' and moved it to img.
	picture is sized to 100px.

Modification to Pizza.html to improvement frame rate and resizing:
	1. Optimized imaage for faster upload: significant increase in image loadingtime.

Modification to Style.css to improvement frame rate and resizing:
	1. .mover class modified to include 'will-change: transform' and 'transform: translateZ(0)' and 'backface-visibility: hidden' and browser specific   '-webkit-transform: translateZ(0);''
  -moz-transform: translateZ(0);'. using these hardware accelerated css properties will provide preformance increase in various types of browsers and devices.


Modification to Main.js to improvement frame rate and resizing:
	1. Based on a reviewers recomendation i included 'use strict'; inside functions in main.js file.
	2. Optimized for loops by declaring variables outside the for loop in instances where call to the DOM is required in order to reduce Jank.
	3. To avoid syncronous layout of moving pizzas, I used Ilyas' Demo found https://www.igvita.com/slides/2012/devtools-tips-and-tricks/jank-demo.html. this moves the sliding background based on scroll position.
	4. decreased the amount of pizzas to be uploaded to the screen.

Gulp Task Runner was used in experimenting with minification, concatenation, and uglifying. I did not include compact code since i am not experienced it in it enough, but i am realizing great benefit and accelerated production of code by it once i get handle for it.

here are the sources that helped me with the project in addition to Udacity course videos and Github Poject examples


http://deanhume.com/home/blogpost/web-page-performance---profiling-paint-times/91
https://www.youtube.com/watch?v=LzELw8k1FEY
http://www.html5rocks.com/en/tutorials/speed/layers/
http://wilsonpage.co.uk/preventing-layout-thrashing/
http://www.html5rocks.com/en/tutorials/speed/animations/

http://gulpjs.com/plugins/
https://css-tricks.com/almanac/properties/b/backface-visibility/

