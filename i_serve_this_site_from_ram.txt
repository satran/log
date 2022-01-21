I serve this site from RAM
20/10/2019

**tl;dr**: For the past few days I have been serving this site completely from RAM. No JavaScript and no third party cookies. Benchmark on the latest raspberry pi has been 3500-4500 requests/second. This is the story of how and why I did it.


I have been using Github to serve my blog for quite sometime now. It was around 2012 that I did so. Github was convenient. It provided me with a simple interface to serve markdown pages. A convenient way to get a blog running. 

But along came HTTP2 and the need for HTTPS everywhere. Mozilla voiced out HTTPS with pomp and glory. Google started punishing HTTP only sites. Thus began my hunt for a HTTPS solution for my blog. I couldn't find out how to setup a custom domain with TLS support on GitHub pages.It may well be that I'm just lazy to search well. So I decided to search for alternatives. 

I looked at numerous blog providers, Wordpress, Ghost, Blogger, and several others. I also investigated the cost of running it on my own. With Letsencrypt providing free TLS certificate and cheap hosting, the most cost effective one was hosting it by myself. There is a cost to manage it but it comes with absolute flexibility. And the cost turns out to be that of a hipster coffee every month. And if I get more traffic I could skip two or three coffees a month. So the answer was clear: self hosting.

Since GitHub used Jekyll for my blog my first idea was to use NGINX and serve the Jekyll generated static files. This way the effort was very minimal. But using Jekyll when I had the choice not to wasn't smart. Should I run Wordpress? It needed a database. Ghost also needs a database and it runs on JavaScript. No thanks, not for a simple text based blog. I code mostly in Go, I considered Hugo even though I may never be in the position of modifying it. As with every hobby project I thought this might be the best time to write my own static file generator.

I started looking through all the articles I had written, thinking how should I go about formatting it. I realized I had very few, just 30 at the time of writing this article. And even if I did write quite a lot say a hundred or a thousand more these were just plain text files. I wondered how much of memory would it take if I just served the generated HTML from memory rather than writing it to a file. I calculated the size of both images and posts. It was just 3.1 MB. The cheapest server had 2GB of RAM. The text files and images would never need that. 

Thus started my short journey of writing my own blog server. With the apache benchmark tool on a RaspberryPi 4 I got a maximum of ~4500 request per second. I am yet to benchmark it with TLS and on the actual machine. But I have my high hopes. The site is very minimal, no frills, no JavaScript, and no cookies and this is the best part, I have almost complete control of the site. 

I have shared the code in GitHub: https://github.com/satran/blogengine. It serves the articles written in https://github.com/satran/blog. I’m not sure if this would serve anybody else. But if you are curious of serving your blog using this do let me know with a feature request or pull request.

