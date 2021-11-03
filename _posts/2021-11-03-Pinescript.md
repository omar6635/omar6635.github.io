---
title:  "Pinescript tutorial 1"
date:   2021-11-02 13:06:39 +0100
categories: pinescript
---
Welcome to the first part of the Pinescript tutorial series! Here you will learn how to leverage the power of Pinescript to create a robust and fundamentally sound Algorithm all in Tradingview.

If you don't have any previous programming background, don't worry, this series was made with beginners in mind. I will try to keep the use of jargon and terminology to a minimum and at the same time, explain the different terms and definitions you have to know to understand the logic behind pinescript.

For the first tutorial, I'll teach you how to view an indicator's code in TV (Tradingview) and explain some syntax. For this example we will use a Moving Average, commonly abbreviated to MA.

Start by going to the <a href="https://tradingview.com" target="_blank">TV website</a> and sign up if you don't already have an account. Once you're done, open the charts by clicking the little icon at the top left and on then on "Chart".

You're almost ready, now you just need to insert the indicator to your chart. Do this by clicking at the "Fx" icon at the top middle and typing "Moving Average" in the search bar. Choose the first result from the built-in indicators.

A blue moving average should get plotted on your chart. You will also see the indicator name and its value on the current candle you are hovering on with your crosshair at the top left. Hovering over this will give you a couple of options. The one we're interested in is the source code option represented by a two curly brackets icon. Clicking on this should prompt the Pine Editor to open from the bottom. You should see the following code:


The first line defines the version of pinescript and HAS to be prefixed by two slashes and an at sign so the pinescript compiler (the tool that runs the program) can run it. Code written in previous versions will have a different version number, __don't change that number on those indicators__ unless you're ready for some serious bug fixing.

Different information is provided for the `indicator()` function using __parameters__. Parameters are values that a function can take and process. Some parameters are mandatory and some are optional.

Variables like `len` are defined by using first typing a variable name and then an equal sign and a value for that variable. In the case of `len`, the value is an __integer input function__. Integer means that the value is a whole number and input means the user can change it without having to change the code using the cogwheel icon. I'll teach you how to do this later.  

In the example of the variable `out` has the value `ta.sma`. `ta` stands for "Technical Analysis" and `sma` for "Simple Moving Average". The SMA belongs the the TA family of indicators, which explains the syntax. This function takes two mandatory parameters and returns a Simple moving average. 

> Pro tip: holding "ctrl" and clicking on a function pulls up the TV documentation. Here you will find info about the function and its different arguments. If you ever forget the syntax for something, don't forget to use it!  






To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
