---
date: 2016-12-31
linktitle: How-To-Get-A-Perfect-PageSpeed-Score
menu:
  main:
    parent: thoughts
prev: /tutorials/mathjax
title: Perfecting Google PageSpeed
tags: [ "100 PageSpeed Score", "PageSpeed Insights", "SEO Hacks", "Blog Optimisation"]
weight: 10
---

I'm getting pretty serious about blogging right now and I’m curious to know how much traffic and subscribers I can acquire by "correctly" applying SEO, researching keywords and building backlinks. I actually think this shouldn’t be too difficult using Wordpress and its million or so plugins dedicated to climbing Google rankings, but I’ve decided to try achieve the same results using a simple static website. Worst comes to worst, I’ll just switch back to Wordpress, but for now I’m really happy about using Hugo.

I know content is king and that clearly doesn't happen overnight, but for all the other things we can improve on right now, there’s speed. There's nothing worse than a slow clunky AND ugly website in today’s age and Google has also officially stated that speed is a factor used in their ranking algorithm.

![Google Speed algorithm](https://cdn-images-1.medium.com/max/800/1*P4yxY8HBaW34SW5Bbng2LQ.jpeg)

In order for my blog to have its best foot forward, I ran this blog on Google PageSpeed. The result? Not bad, but not great either:

![Google PageSpeed Desktop](https://cdn-images-1.medium.com/max/800/1*EiF6ESXTogj-_K-TsnNXVw.png)

![Google PageSpeed Mobile](https://cdn-images-1.medium.com/max/800/1*ok6h_sV490Bizj2uyL0fkg.png)

### Eliminating Render-blocking JavaScript and CSS
Every website that I’ve ever entered into Google’s Pagespeed tool has complained about render-blocking Javascript and CSS. Javascript is used to program the behaviour of web pages and CSS specifies the layout, and what this means is that they are keeping the page from loading as quickly as possible.

![Blocking CSS Resources](https://cdn-images-1.medium.com/max/800/1*4uAo4OWeBr5Do2rGhJ3aqw.png)

### Combining CSS files
My blog doesn’t have any render-blocking Javascript, but it does have 3 blocking CSS resources. This means my blog cannot begin showing the page until all the CSS files are downloaded and parsed. To try and fix this, I combined the 3 CSS files into 1 and removed the redundant CSS calls.

### Minifying CSS
Minifying CSS is the process of removing unnecessary or redundant data to reduce the size of the file. I pasted my CSS into a free online minifying tool which stripped the whitespaces away, bringing my mobile ranking to 87/100 and desktop ranking to 94/100. Not bad.

### Inline CSS

Yet, Google was still unhappy about my CSS. To get around this, I was either going to have to add scripts to defer my CSS file, or inline my CSS by adding everything inside the html file. I first tried deferring the CSS which somehow introduced JavaScript issues, so I ended up applying the latter option. Seriously seems super hacky, but it got the job done anyway!

### Leverage browser caching
![PageSpeed Browser Caching](https://cdn-images-1.medium.com/max/800/1*jkw_nQnE_rvj6JmcDXSZkw.png)
It’s pretty ironic how including Google Analytics will result in fetching a script which is cachable for only 2 hours. To leverage browser caching, the rule PageSpeed looks for is caching for at least 8 days. To workaround this, I found a script on StackOverflow to host the script outside of Google.

```javascript
<script async='async' src='https://cdn.jsdelivr.net/ga-lite/latest/ga-lite.min.js'></script> <script>var galite=galite||{};galite.UA="xx-xxxxxxx-x";</script>
```

### The Final Result 😎
![PageSpeed 100/100 score](https://cdn-images-1.medium.com/max/800/1*QQid6blG9i03ETv1-2-RWQ.png)
