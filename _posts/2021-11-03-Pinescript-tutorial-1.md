---
title:  "Pinescript tutorial 1"
date:   2021-11-02 13:06:39 +0100
categories: pinescript
---
Welcome to the first part of the Pinescript tutorial series! Here you will learn how to leverage the power of Pinescript to create a robust and fundamentally sound Algorithm all in Tradingview.

If you don't have any previous programming background, don't worry, this series was made with beginners in mind. I will try to keep the use of jargon and terminology to a minimum and at the same time, explain the different terms and definitions you have to know to understand the logic behind pinescript.

For the first tutorial, I'll teach you how to view an indicator's code in TV (Tradingview) and explain some syntax. For this example we will use a Moving Average, commonly abbreviated to MA.

Start by going to the <a href="https://tradingview.com" target="_blank">TV website</a> and sign up if you don't already have an account. Once you're done, open the charts by clicking the little icon at the top left and on then on "Chart".

You're almost ready, now you just need to insert the indicator into your chart. Do this by clicking at the "Fx" icon at the top middle and typing "Moving Average" in the search bar. Choose the first result from the built-in indicators.

A blue moving average should get plotted on your chart. You will also see the indicator name and its value on the current candle you are hovering on with your crosshair at the top left. Hovering over this will give you a couple of options. The one we're interested in is the source code option represented by a two curly brackets icon. Clicking on this should prompt the Pine Editor to open from the bottom. You should see the following code:


<pre><code><span style="color: gray;">//@version=5</span>
<span style="color:#00B6FF;">indicator</span>(title=<span style="color:#79F293">"Moving Average"</span>, shorttitle=<span style="color:#79F293">"MA"</span>, overlay=<span style="color:#FA941E">true</span>, timeframe="", timeframe_gaps=<span style="color:#FA941E">true</span>)
len = <span style="color:#00B6FF;">input.int</span>(<span style="color:#FA941E;">9</span>, minval=<span style="color:#FA941E;">1</span>, title=<span style="color:#79F293;">"Length"</span>)
src = <span style="color:#00B6FF;">input</span>(<span style="color:#F73B3B;">close</span>, title=<span style="color:#79F293">"Source"</span>)
offset = <span style="color:#00B6FF;">input.int</span>(title=<span style="color:#00B6FF;">"Offset"</span>, defval=<span style="color:#FA941E">0</span>, minval=<span style="color:#FA941E">-500</span>, maxval=<span style="color:#FA941E">500</span>)
out = <span style="color:#00B6FF;">ta.sma</span>(src, len)
<span style="color:#00B6FF;">plot</span>(out, color=<span style="color:#F73B3B;">color.blue</span>, title=<span style="color:#79F293">"MA"</span>, offset=offset)
</code></pre>

The first line defines the version of pinescript and *HAS* to be prefixed by two slashes and an at sign so the pinescript compiler (the tool that runs the program) can run it. Code written in previous versions will have a different version number, __don't change that number on those indicators__ unless you're ready for some serious bug fixing.

Different information is provided for the `indicator()` function using parameters. Parameters are values that a function can take and process. Some parameters are mandatory and some are optional.

Variables like `len` are defined by using first typing a variable name and then an equal sign and a value for that variable. In the case of `len`, the value is an integer input function. Integer means that the value is a whole number and input means the user can change it without having to change the code using the cogwheel icon. I'll teach you how to do this later.  

In the example of the variable `out` has the value `ta.sma`. `ta` stands for "Technical Analysis" and `sma` for "Simple Moving Average". The SMA belongs the the TA family of indicators, which explains the syntax. This function takes two mandatory parameters and returns a Simple Moving Average. 

> Pro tip: holding "ctrl" and clicking on a function pulls up the TV documentation. Here you will find info about the function and its different arguments. If you ever forget the syntax for something, don't forget to use it!  

The created indicator that was saved in the `out` variable is then outputted to the chart using the `plot` function.

Alright! That's it for this first tutorial. I hope you learned something new. The link for part 2 can be found [here](../02/Pinescript-tutorial-2.html).