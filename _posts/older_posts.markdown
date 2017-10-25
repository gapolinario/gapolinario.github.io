<h2>
Gnuplot Every
</h2>



Official documentation <a href="http://gnuplot.sourceforge.net/docs_4.2/node121.html">here</a>.



Wednesday, August 9, 2017

<!-- end of blog post-->

<h2>
Uninstall programs and remove repositories
</h2>


Resources
https://askubuntu.com/questions/307/how-can-ppas-be-removed
https://askubuntu.com/questions/1143/how-can-i-uninstall-software




Tuesday, August 8, 2017



<!-- end of blog post-->




<h2>
Linux display manager
</h2>






Resources on this subject are clearly explained <a href="https://askubuntu.com/questions/829108/what-is-gdm3-kdm-lightdm-how-to-install-and-remove-them">here</a>.



Tuesday, August 8, 2017



<!-- end of blog post-->




<h2>
Terminator shortcuts
</h2>


Some of the useful shortcuts I use on Terminator are:


<ul>
<li> Ctrl+Shift+E or Ctrl+Shift+O to split the screen vertically/horizontally </li>
<li> Alt+Arrows to circle through terminals </li>
<li> Ctrl+Shift+X focuses on the currently working terminal </li>
</ul>


Tuesday, August 8, 2017



<!-- end of blog post-->



<h2>
VLC shortcuts
</h2>


This is a list of VLC shortcuts tailored for my needs.


<ul>
<li> E               frame by frame </li>
<li> F               fullscreen </li>
<li> V               subtitles on/off </li>
<li> Ctrl+Up/Down    volume up/down </li>
<li> Shift+Left/Right    +/- 3 seconds </li>
<li> Alt+Left/Right      +/- 10 seconds </li>
<li> Ctrl+Left/Right     +/- 1 minute </li>
<li> []=                 10% slower/10% faster/normal speed </li>


Saturday, July 29, 2017



<!-- end of blog post-->

<h2>
Film stills
</h2>


This is just to save the place where I can find great film stills, of classic films,
arranged by title, director, and even cinematographer. The site is <a href="https://film-grab.com/">FilmGrab</a>



One more problem solved in Linux. I just don't know if the Spotify Windows user had his problem solved.



Recently the problem came back and was harder to solve, I had to delete both preference files,
one of which includes login data:


<p class="code">
rm ~/.config/spotify/prefs ~/.config/spotify/window_position.prefs



It works and resets standard configuration, but after that one has to log in again.
Maybe I can manually alter the prefs file to change window starting position,
and place it where I can minimize/maximize properly. Leave this to a later time.
Another solution is to only remove lines relative to window position, this is also something to try,
remember I have backups for both prefs and window_position, so that the situation can be reversed.



Saturday, July 29, 2017



<!-- end of blog post-->





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
References on Latex Fonts
</h2>


<a href="https://tex.stackexchange.com/a/25251/107590">Font families and
selecting font</a>




Wednesday, July 26, 2017



<!-- end of blog post-->




<h2>
Setting up a backup on Linux
</h2>


An interesting option to backup a filesystem is


<p class="code">
$ rsync -av /home/ /media/backup_drive/



This is very similar to the command I use to send updates to this page.



a is archive, equivalent to -rlptgoD
r is recursive
l copies symlinks as symlinks
p is preserve permissions
t is preserve times
g is preserve group
o is preserver owner
n is a dry run, nothing really happens
--delete clears files that were deleted in the original folder, it doesn't acumulate
z is compress data



I added an alias to the ~/.bashrc file to make backup even easier. Just add the line:


<p class="code">
alias backup="rsync -av /home/ /media/gabriel/.../backup/ --delete"



Then all you have to do is run "backup" and the computer will do the task.
Remember to apply the changes to the bashrc with "source ~/.bashrc"
This can be made periodic with cron or anacron, maybe someday I will talk about it.



Tuesday, July 18, 2017



<!-- end of blog post-->




<h2>
Great Mathematica resource
</h2>


This time I am here to report on a great place to study more about Mathematica programming.
The <a href="http://www.mathprogramming-intro.org/">book</a> by Leonid Schifrin, extensive
mathematica.stackexchange user, has all the details about programming logics in mathematics.
This is different from procedural programming, and is more oriented to lists and functions,
the book was a great resource on learning about how Mathematica is structured. It also
has great examples, it is very easy to follow the examples alongside with Mathematica,
and verifiy by yourself what the book is saying.



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



References on the subject are <a href="http://blog.wolfram.com/2017/05/17/wolframscript-run-your-code-from-anywhere/">
here</a> and in Wolfram documentation.






Friday, July 14, 2017



<!-- end of blog post-->




<h2>
Report on Linux Mint 18.2
</h2>


After many years of continuous linux use and barely none of windows, with some problems in
the middle of the way, here I am with my first full installation of Linux on a computer.
It was a breeze and is flowing very well. Soon I am going to write more about it.



Mention how Antergos XFCE was important in the customization process, then I installed
Ubuntu Gnome at UFRJ and had that problem with dual boot. Then mention that I had a
problem at the home computer with virtual box, still not recognized, I bought an
external hd and here I am with Mint Cinnamon.



The installation was done on wednesday, july 12. Then final customization was done
on thursday, july 13, and very quickly I had the computer up and running



I had a strange problem, my screen was rotated when I turned on the computer.
Nothing happened on the test with the live usb, only when I turn on the computer for the
first time I saw the screen was rotated. Some incompatibility with my laptop which has
this rotating screen thing. The solution I found on the web was:


<p class="code">
$ gsettings set org.cinnamon.settings-daemon.peripherals.touchscreen orientation-lock  true



I don't know what it does, found it <a href="https://github.com/linuxmint/Cinnamon/issues/6059">
here</a>.






Friday, July 14, 2017



<!-- end of blog post-->




<h2>
Remote Logout
</h2>


I had a problem with a remote ssh session. A problem I still have to figure out how to solve:
at UFRJ I can log to CTG-dev and leave the computer logged for hours without touching it,
the connection is not lost. Here at home, if I connect to ssh, I have to always do something
at the terminal, or the connection is lost. I don't know if it's some configuration I can
fiddle with, or it is the fact that when at UFRJ the IPs are from the same place, and
that's why connection doesn't fall, I have to investigate that.



So the connection was lost and I was still connected, I logged in again and logged out of
the old session remotely, using:


<p class="code">
$ pkill -9 -t pts/9



First run 'tty', it shows what is your current session. Then run 'w', it shows all logged in user
sessions. When I didn't know that I used to run 'last' and it also showed the last sessions,
including the users logged in. 'w' is shorter and to the point.



Learned this <a href="https://superuser.com/questions/193168/how-can-i-logout-an-open-remote-ssh-session">
here</a>. StackExchange is always there for the solution.



Friday, July 14, 2017



<!-- end of blog post-->




<h2>
Checksums
</h2>


We use checksums to make sure that a file was correctly downloaded,
especially large files, like isos. Or the Mathematica installation.
Linux Mint, for instance, provides the checksum for one of its installation
iso <a href="https://ftp.heanet.ie/mirrors/linuxmint.com/stable/18.2/sha256sum.txt">here</a>.



To check the integrity, you can run


<p class="code">
$ sha256sum -b ...iso



The option b reads the iso in binary mode. This is the first time I use this option and
it always worked, so I'm not sure what it did before. Or you may use the -c option
to read the sum from a file and check it. Try this:


<p class="code">
$ sha256sum --ignore-missing -c ...txt



Where the .txt file has a list of checksums. The option --ignore-missing tells the
program to ignore problems if some of the files are missing, because I downloaded only
one of the versions, not all of them.



Linux Mint, beginner friendly as always, provides a <a href="https://linuxmint.com/verify.php">
page</a> where this is throughly explained.



Wednesday, July 12, 2017



<!-- end of blog post-->




<h2>
Convert a series of images to a PDF
</h2>


If you just took a series of pictures, you can turn them into a single pdf very simply,
with the imagemagick program. If it is not installed, run


<p class="code">
$ sudo apt-get install imagemagick


Then, to convert the pictures, use

<p class="code">$ convert image1.jpg image2.png image3.bmp output.pdf

This works with a number of extensions. In particular, if your pictures are named in series, like
page1, page2, page3, etc. You can try

<p class="code">
$ convert page*.jpg output.pdf



And it works just fine



More on this and a GUI way to do it at <a href="https://itsfoss.com/convert-multiple-images-pdf-ubuntu-1304/">How To Geek</a>.



Monday, July 3, 2017



<!-- end of blog post-->






<h2>
How to find out your windows product key
</h2>


A windows license is expensive and keeping your product key
is something you might need.
You can look it up under the computer (if it is a laptop),
usually close to the battery. But even if it has already
erased, you can find it out using the computer.



Open 'Microsoft Powershell' and type


<p class="code">
(Get-WmiObject -query 'select * from SoftwareLicensingService').OA3xOriginalProductKey



If it doesn't work, there is software that does that, like ProduKey,
though I didn't try it. I also don't know what is the Powershell,
how it differs from Run and from the Command Prompt.



I found out about this at <a href="https://www.howtogeek.com/206329/how-to-find-your-lost-windows-or-office-product-keys/">How To Geek</a>.



Wednesday, June 28, 2017



<!-- end of blog post-->




<h2>Installing fonts on Ubuntu (and unzip)</h2>


I downloaded a big file with fonts. An observation is that these font
compressed files are valuable, always keep them for future computers.
To install them, just throw everything in the /usr/local/share/fonts/
folder, like this:


<p class="code">
$ sudo unzip fonts.zip -d /usr/local/share/fonts



This also illustrates how to unzip to a specific folder.



The awesome font collection came from <a href="https://www.typewolf.com/google-fonts">Typewolf</a>.



Soon after that I tried to install the equally awesome package of
fonts from <a href="http://platowebdesign.com/articles/fonts/">Plato</a>,
but they are in rar format and I didn't know how to unrar from the terminal.
What I did was:


<p class="code">
$ sudo file-roller plato_fonts.rar



And I opened the compressed files manager with super user powers,
so I could extract the files to the proper directory.
After all this I was prepared to rock with my presentations.



But to install the Plato Fonts collection, this time I tried


<p class="code">
$ sudo file-roller plato.rar -e /usr/local/share/fonts/



This returns a warning message, but in the end it works fine



Tuesday, June 27, 2017



<!-- end of blog post-->




<h2>
What I have learned about web development
</h2>


Since I started building my website, I have learned much about web development
and I even look critically at webpages in general, especially to webpages of physicists.
I have a blog post on that topic (which I can't link to, because this page
is very static so far, but it should get better in the future.)



If you are just beginning, Codecademy is the best place to start. The basic is learning
HTML and CSS to have a page and to build its style. Some bootstrap, if you want your web
page to be responsive (responsive is a tech-savy keyword, means that your page works
on any device: desktop, smartphone, tablet, ipod, projecting screens).



If you want interactivity, you'd want to learn some Javascript and jQuery. jQuery is a
Javascript library which makes things easier, because programming in pure Javascript
is a difficult mission.



Monday, June 26, 2017



<!-- end of blog post-->




<h2>
Overwrite local files on Git Pull
</h2>


First, a warning. The topic of this post refers to dangerous and not recommended practices. It refers to times
when I was less skilled at Git. Doesn't mean that nowadays I'm a git wizard, only means that I have learned
some safety practices since then.



Let's begin with the way I used to do it. When there was a merge conflict, I would simply erase the local
changes with


<p class="code">
$ git fetch --all
$ git reset --hard origin/master



Of course I could only do it because I was the only one fiddling with the files and I knew which version was
the up to date one, and what changes I could discard. Then I learned some git (there's a codecademy course for
that, and numerous tutorials on the web). They showed me I should not pull, instead I should fetch and merge:


<p class="code">
$ git fetch --all
$ git merge origin/master


or the lazy and somewhat dangerous version

<p class="code">
$ git fetch --all && git merge origin/master



I learned this <a href="https://www.quora.com/How-do-I-force-Git-to-overwrite-local-files-on-pull">here</a>.



Monday, June 26, 2017



<!-- end of blog post-->




<h2>
Vim display colors of gnuplot
</h2>


I usually write my gnuplots files with a .gp extension and vim does not recognize it as gnuplot automatically.
To do so, one can type on vim


<p class="code">
:setf gnuplot



To change this permanently, add the following lines to your ~/.vimrc file:


<p class="code">
" Set the type for the file type and override if file type
" already has detected
au BufRead,BufNewFile *.gp set filetype=gnuplot



To learn more, <a href="http://learnvimscriptthehardway.stevelosh.com/">this website</a> has many resources on vim scripts,
from customization (editing the ~/.vimrc file, like we just did), to more complex scripting and package building.



Monday, June 26, 2017



<!-- end of blog post-->




<h2>
A video: The Case for Land Art
</h2>


The Art Assignment channel published this video, <a href="https://www.youtube.com/watch?v=STW0eZDsKVg">
The Case for Land Art</a>, to make us think about the purpose and endeavor of Land Art, a sort of art
form which interacts with the natural world, either by displacing its elements to a gallery environment,
or by making art work directly in the environment.



The first instance of Land Art I heard about was A Line Made by Walking, by Richard Long, and it is
mentioned in the video (1:52), this and other works are in the Will Gompertz book, "Isso é arte?".
What Richard Long was walk on a straigth line on grass until his footsteps marked a line on the ground.
When I read about it in the book, I didn't look for the picture, and what I imagined was a curved line,
more like paths in a farm, leading somewhere. This is a more geometric, artsy and detached shape.
The straigth line reminds us that this is only art, and is not leading anywhere, this is not a short
path or a necessary path, this is just a path.



It also mentions there is a spectrum of what is Land Art and what is not. This led me to think about
the Inhotim museum, which touches several aspects of contemporary art. For instance, it has several
gardens, and there was another text I read these days which mentioned several artists who
planned gardens. On a grander view, Roberto Burle Marx planned the whole museum, which has a series
of marked (with stones) or unmarked (footsteps only) paths, winding and bifurcating. On a smaller,
more specific view, there is a garden designed by Yayoi Kusama, with several floating sivler balls
on the water.



And there is all the art around Inhotim. Some are sculptures, or works of art laid out on the grass,
these are distinctely marked as artworks, and while not detached from their environment, they
are distinct. This is art on the land, but it is not land art. There are several giant pavillions,
which act on a larger scale just like the sculptures. But there is the slide. A huge slide built
on art. There are the brick letters and the names spread on the grass. There is the beam drop,
taking away from the landscapes of the city (concrete) and putting it in the wild, a sea of
concrete and concrete beams.



An artist whom, on several occasions in Inhotim, interacts with the land is Olafur Elliason. There
is the kaleidoscope, used for observing the environment. And there is the igloo, it is small and composes
the environment around it with a psychedelic blinking fountain (inside), and a silvery unearthy igloo
on the outside.



Throughout all of the Inhotim, there are instances of art interacting with the environment in varied ways,
sometimes more as land art, sometimes less. This only illustrates the wide spectrum of uses artists
can make of their environment. Probably, the great attraction to all audiences produced by Inhotim
is in great part due to the mixture of nature so wide and open which are a rare view in the city,
and man made sites, more common to the sight, but at the same time so strange, so unusual,
so purposeless and useless in their strange shapes and materials.



Saturday, June 25, 2017



<!-- end of blog post-->




<h2>
A list of quotes
</h2>


If it wasn't obvious from a map, you can tell the crater is in America since, like many things America,
it is privately owned.
Lisa Randall, Dark Matter and Dinosaurs



In 1980, the group led by Walter and Luiz Alvarez proposed that a big meteoroid had collided with the Earth
and rained down rare earth metals, including iridium
Lisa Randall, Dark Matter and Dinosaurs



It had long since come to my attention that people of accomplishments rarely sat back and let things
happen to them. They went out and happened to things.
Leonardo da Vinci



Friday, June 23, 2017



<!-- end of blog post-->




<h2>
How to view disk usage
</h2>

Display usage of disk for all partitions, including free space, with

<p class="code">
$ df -h



-h means human readable form.



And to display size of a single folder, or file, use


<p class="code">
$ du -sh /path-to-folder/


One nice trick is how to display size of all folders

<p class="code">
$ du -sh */


Take a look at the manual entries for df and du for more information.


Friday, June 23, 2017



<!-- end of blog post-->

<h2>
Finding duplicate files
</h2>


fdupes is a powerful program that looks for duplicate files on your computer even if they have different names.
To search the folders Folder1, Folder2, etc for duplicate files, just run


<p class="code">
$ fdupes -r Folder1 Folder2 ... >> dupes.log



The output might be quite long, this is way I redirected it to a differente file.
The program offers several options, like keeping only the first file and deleting all others,
or you can manually look at the log and decide what to do with the duplicated files.



Monday, June 19, 2017



<!-- end of blog post-->





<h2>
Customize your command line
</h2>


The PS1 variables stores the look of you command line prompt, you can take a look at its format,
right now, with

<p class="code">
$ echo $PS1



To change this look, I added the following line to the '~/.bashrc' file:


<p class="code">
$ export PS1="\[\033[1;36m\]\u@\h \[\033[0;36m\]\W > \[$(tput sgr0)\]"


This way, the terminal will be bold light blue (1;36m) and normal light blue (0;36m), you can choose other colors
and other formats for the terminal.


References on these colors are available at <a href="http://misc.flogisoft.com/bash/tip_colors_and_formatting">this site</a>, for instance.

There are also <a href="http://bashrcgenerator.com/">bash rc generators</a>, which help you build one.



Then make changes permanent with


<p class="code">
$ source ~/.bashrc



Sunday, June 18, 2017



<!-- end of blog post-->




<h2>
Scheduling tasks on Ubuntu
</h2>


Run 'crontab -e' to open the scheduling and add your jobs in the following format


<p class="code">
MIN HOUR DOM MON DOW CMD



These words mean:
MIN: minute
HOUR: hour
DOM: day of month
MON: month (from 1 to 12)
DOW: day of week (from 0 to 6, 0 is Sunday, on some systems it is 7)
And finally CMD is the command you want to execute at the established time.


Fill these fields with the appropriate numbers, or a * if the task is to be executed always, that is,
every minute, or every hour. You can use intervals too, like 09-18.

To view your crontabs, use 'crontab -l', this shows the crontabs for the user currently logged in.

You can else set up intervals for the task, thus */10 in the minute field means every 10 minutes.

There are also special keywords which can be used instead of the time assignment, they are: @yearly, @daily, @hourly, @monthly and @reboot.

Nice reference at <a href="http://www.thegeekstuff.com/2009/06/15-practical-crontab-examples">The Geek Stuff</a>.


Sunday, June 18, 2017



<!-- end of blog post-->




<h2>
Tunneling traffic on Firefox
</h2>


How can I use Firefox as if I were in another computer?
You can log in to a remote computer

<p class="code">
$ ssh user@ip -D 1337


and '-D 1337' tells ssh to launch a SOCKS server on port 1337 locally.

Then open firefox, close all tabs, and go to Settings (the sandwich on the top right),
look for Preferences -> Advanced and, under Connection, go to Settings.

There, check 'Manual proxy configuration' and the line you need to change is SOCKS host:
change it to 'localhost' and port '1337'.

And you are done

Look up <a href="https://askubuntu.com/questions/469582/how-do-i-set-up-a-local-socks-proxy-that-tunnels-traffic-through-ssh">this question</a> for some details and more ssh options.

When you are done, go back to 'no proxy' on the Connection settings.


Saturday, June 17, 2017



<!-- end of blog post-->




<h2>
Burn ISO to a Live USB
</h2>

Download the .iso file, open a terminal and navigate to its folder, then run

<p class="code">
$ sudo -i


List the partitions on the computer

<p class="code">
# lsblk


This will show you the name of the partition you want to format as a live USB and
tell you whether it is mounted or not. If it is, remember to unmount it

<p class="code">
# umount /dev/sdb1


Then comes the burning part

<p class="code">
# dd bs=4M if=myfile.iso of=/dev/sdb && sync


Notice this is not /sdb1/, but /sdb, simply. When you are done, don't forget to leave root

You may test the installation with a virtual machine, such as qemu. By running

<p class="code">
$ qemu-system-x86_64 -hda /dev/sdb


Finally, you can clean the USB drive with

<p class="code">
$ wipefs --all /dev/sdx



Friday, June 16, 2017



<!-- end of blog post-->
