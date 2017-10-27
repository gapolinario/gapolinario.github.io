<h2>
Problems with Spotify
</h2>


I had this problem where Spotify was always full screen, even hiding the taskbar, at the bottom
of the screen. I did some research and found <a href="https://community.spotify.com/t5/Desktop-Linux-Windows-Web-Player/Spotify-open-in-full-screen-cannot-access-taskbar-anymore/td-p/1044311">this</a> page reporting the
same problem. Although the OP says he had the problem using Windows 7, the accepted answer
has a strangely linux-looking format, it tells you to remove the "~/.config/spotify/window_position.prefs"
file, then open Spotify again. Indeed, it worked.

One more problem solved in Linux. I just don't know if the Spotify Windows user had his problem solved.

Saturday, July 29, 2017


<!-- end of blog post-->





<h2>
Great Mathematica resource
</h2>


This time I am here to report on a great place to study more about Mathematica programming.
The [book][leonid] by Leonid Schifrin, extensive
mathematica.stackexchange user, has all the details about programming logics in mathematics.
This is different from procedural programming, and is more oriented to lists and functions,
the book was a great resource on learning about how Mathematica is structured. It also
has great examples, it is very easy to follow the examples alongside with Mathematica,
and verifiy by yourself what the book is saying.

[This][math-se] is also a good compilation of resources


[leonid]: http://www.mathprogramming-intro.org/
[math-se]: https://mathematica.stackexchange.com/questions/18/where-can-i-find-examples-of-good-mathematica-programming-practice

Tuesday, July 18, 2017



<!-- end of blog post-->




<h2>
Hardware and Graphics Cards on Linux
</h2>


To find out what is my graphics card, I tried


<p class="code">
$ lspci -vnn | grep VGA -A 12



This command shows all peripherals connected to the computer. VGA looks for
the graphics card line. On my computer, the output was



Where the model of the graphics card is Intel Broadwell-U Integrated Graphics [8086:161e]. This is on the line
of the 'VGA compatible controller'. The first number is the manufacturer, the second is the model.
There is also a Kernel driver in use also, but I looked for it in another manner, as we'll see.



I knew what is the model of my graphics card and I also wanted to know that graphics card driver is running. Is
it intel or not? I had this question after looking up intel on the web and found out they have open source
software for their graphics cards (not fact checked, but that is what they say). I then run


<p class="code">
$ lshw -c video



lshw is used to show all information on the hardware. In the output there is 'configuration driver',
which says what is the graphics driver in use.



Tuesday, July 18, 2017



<!-- end of blog post-->





<h2>
Reports on a failure: BB on Linux
</h2>


I tried to install the security module for Banco do Brasil in Linux. They have an executable,
which you can just download, make executable and run, and also have a .deb package.
From the website, it looks like they showed real interest in doing something that works easily
for Linux. In the past, we had to install Java from Oracle for the bank software to work.
Apparently not anymore, the only problem is that I tried both approaches and none of them
worked.
I should try one more time, but so far BB has failed me on the computer.




Tuesday, July 18, 2017



<!-- end of blog post-->




<h2>
Using Wolframscripts
</h2>

Works well

References on the subject are [here][wolframscript] and in Wolfram documentation.

[wolframscript]: http://blog.wolfram.com/2017/05/17/wolframscript-run-your-code-from-anywhere/


Friday, July 14, 2017



<!-- end of blog post-->
