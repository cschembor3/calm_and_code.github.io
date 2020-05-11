---
layout: post
title:  "Welcome to Calm and Code"
date:   2020-05-02 10:50:45 -0400
categories: jekyll update
---

Welcome to Calm and Code! I'm a software engineer roughly 2 years into my career. I want to be up front about this to not have an excuse, per-say, but more of an explanation for when I inevitably am either naive or come across like I know more than I really do. This goes for not only when I am writing about software, but also anything else that makes its way on here.

This brings me to the first purpose of this post: what is the goal of this site?
To be perfectly honest, I am still not really sure. I won't lie and say that the hundreds of Medium articles I've come across over the (relatively) few years didn't play some sort of FOMO role.
I'm currently working as a mobile engineer, focusing mainly on iOS development. Many of my postings will likely fall under this category, however I also enjoy web development and some lower level stuff, so they may make their way here as well.

I also like expressing my thoughts in a sort of stream-of-consciousness fashion, so some of my thoughts may come across as rambling. I find this as a good way to think through things, however, and this blog is more for me than you (sorry!).

In addition to the technology focus, I'm interested in mindfulness and minimalism, so I will be writing about these fairly frequently as well. This will be in a similar nature to my writing about code, in that I will more documenting my experiencing in learning more about them then giving some sort of advice on these topics. I hope that in detailing my experiences here, I can better understand them.

The other part of this first post is to talk about something technical! Since this is the first posting on this site, what better thing to talk about than the technology behind it? I'm using [Jekyll](https://jekyllrb.com/) to build this site. Jekyll is basically a framework built on top of ruby to create and maintain static content. The reason I decided to use Jekyll for this is because of the ability it gives me to write my posts in markdown. I could've gone with standard html/css to accomplish the same thing, but I prefer to write my posts in markdown as opposed to html. In addition, Jekyll allows for code formatting such as...

{% highlight elixir %}

def fibonacci(0), do: 1
def fibonacci(1), do: 1
def fibonacci(n), do: fibonacci(n-1) + fibonacci(n-2)

{% endhighlight %}

...which is very convenient.

The default theme is also fairly minimal, which I like. So far there is not so much overhead, so I will likely be sticking with Jekyll, at least for now.