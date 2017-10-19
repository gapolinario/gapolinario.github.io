<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
SciDavis as an alternative to QtiPlot for FisExp
</h2>

<p>
QtiPlot has a restricted trial version and this is not
best practices for a public brazilian university, which should
be using free software, just like any public institution.
The whole world is moving to free software, except for Brasil,
which is moving backwards.
</p>

<p>
But <a href="http://scidavis.sourceforge.net/">SciDavis</a> is open source
and can be easily installed in Ubuntu computers, directly from apt-get
</p>

<p class="code">
sudo apt-get install scidavis
</p>

<p>
And there is the further improvement that one does not need to pronounce it
wrong like "qitplot". Well, I should try and do histograms and
linear fits on it to see if they are really easy.
</p>

<p class="foot">
Tuesday, August 29, 2017
</p>

</div>
</div>

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Installing Guest Additions on a Virtual Machine
</h2>

<p>
This does not look good, some problems might come up.
Take a look at <a href="http://www.techrepublic.com/article/how-to-install-virtualbox-guest-additions-on-a-gui-less-ubuntu-server-host/">
this</a> and <a href="https://askubuntu.com/questions/22743/how-do-i-install-guest-additions-in-a-virtualbox-vm">this</a>
tutorials, the ask ubuntu tutorial is more GUI oriented.
The first time I tried to do this, it didn't work all that well.
</p>

<p class="foot">
Tuesday, August 29, 2017
</p>

</div>
</div>

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Old computer names
</h2>

<p>
olinda: Dell Inspiron 14, my first laptop. Named after the city in Italo Calvino's
The Invisible Cities, not after the city in Pernambuco, although it did influence.
Angelo at UFF helped me install my first Linux system, an Ubuntu. There were later
changes. I used Linux Mint for some time. This was the time I learned how to
write programs.
</p>
<p>
toto: A desktop at home that ran ubuntu for a little while, I want <br>ed it to run fast but
installed a linux system with unity, I have learned much since then. Named after
the dog of Dorothy.
</p>
<p>
kombi: IBM computer at UFRJ, running Ubuntu 15, it was quite slow.
</p>
<p>
chevy: IBM computer was partitioned, and was running antergos under this name.
I wanted it to run faster, so I installed this Antergos XFCE, at first it looked very ugly,
but I watched some videos, did some research and managed a quite pretty customization,
similar to the one I am running now on deluge. An old computer deserves a standard name,
this is the reason behind kombi and chevy, though chevy was sleek and intended to ride
faster (due to XFCE).
</p>
<p>
sopwithcamel: HP Pavillion under dual boot with windows 8, running Linux Mint KDE, it
was not really stable. One day I installed Virtual Box on it, the next day it wouldn't
start the graphics. This was quite a story, but lead me to a path of changing and learning.
It was named after the Peanuts stories, Snoopy often dreams of being a WWI pilot,
where he flies a Sopwith Camel. The Red Baron was his recurring enemy.
</p>
<p>
redbaron: A sandisk 32GB thumb drive. It is mentioned for two reasons. It is a thumbdrive
of large storage which helps a lot at college. And it has a customized name.
</p>
<img src="deluge-desktop.png" title="Deluge desktop" alt="Deluge desktop" style="width:100%;">
<p>
deluge: Dell XPS at UFRJ, ran Ubuntu Gnome for a short while, but it was unstable, later
changed to standard Ubuntu with Gnome Shell. Gnome was heavily customized. Named after
Da Vinci's painting of a flood in Italy, used for my calculations in turbulence.
Using Papyrus icons.
</p>

<img src="byrne-desktop.png" title="Byrne desktop" alt="Byrne desktop" style="width:100%;">
<p>
byrne: HP Pavillion, my first full installation of a Linux system. Even works with
an extra monitor (a TV, connected through HDMi, even the sound plays right).
After David Byrne. Icons here are Ultra-Flat.
</p>

<p class="foot">
Thursday, August 17, 2017
</p>

</div>
</div>

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Git Summary
</h2>

<p>
Still not revised. Badly not revised, by the way.
</p>

<p>

git add -A
git commit -m '&ltyour message&gt'
git push origin master
Basic commands for pushing your commits from local computer to database

git push --force origin master
Force setting local as the default.

git pull origin master
Basic for pulling updates from remote to local computer



git checkout &ltcommit&gt &ltfile&gt
&ltfile&gt is optional
revert &ltfile&gt or whole folder to specified &ltcommit&gt

git fetch
git reset

# puts local machine in sync with remote, cleans changes
git fetch --all
git reset --hard origin/master

git add -A
git commit -m 'Comment'
git push origin git

git pull origin master

git diff        # just like diff, show changes
git log         # show history of commits

git checkout stable     # change to branch stable
git merge new-idea      # merge branch new-idea into branch stable
git branch -d new-idea  # then you may delete branch new-idea, or continue working on it

say you have a flow like

M--N---------O--P--Q on branch master

run git branch dubious, then both master and dubious have the same tree structure
now run

git reset --hard &ltSHA1 sum of commit N&gt

then branch master has reverted to commit N and branch dubious still has the changes up to branch Q.

git fetch origin
git diff master origin/master       #show differences between remote and local
git merge origin/master             #merge imports

git show HEAD
git diff
git checkout HEAD file              #revert file back to HEAD (undo changes)
git reset HEAD file                 #unstage changes
git reset SHA                       # reset to a previous commit

git branch                          #show branches
git branch name                     # open a branch called name
git checkout name                   #go to branch name
git merge name                      #merge branch name with current working branch
git branch -d name                  #delete branch name

git clone remote_location clone_name    #make a copy
git fetch                           #brings changes to local branch
git merge origin/master             # merge local and remote
git push origin branche             #push commits in branch branche to remote
</p>

<p class="foot">
Thursday, August 17, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Configure Bitbucket to connect with an SSH key
</h2>

<p>
Go to the settings on your Bitbucket account and add
the contents of the public key file,
~/.ssh/id_rsa.pub, for instance.
You can copy the contents of that file to the clipboard with
</p>

<p class="code">
cat ~/.ssh/id_rsa.pub | xclip -sel clip
</p>

<p>
Then change the {project-folder}/.git/config file.
Under the heading "remote origin", change the URL from https to ssh,
all the rest of the URL is the same. Apparently
this has to be done for each individual project.
</p>

<p>
Bitbucket has a great
<a href="https://confluence.atlassian.com/bitbucket/set-up-ssh-for-git-728138079.html#">tutorial</a>
that explains all this in more detail. My approach in this text was very practical.
</p>

<p>
In Github, everything works in a similar fashion. Go to settings and add the contents of
the public key. You can clone the project directly with the SSH address and
everything works out of the box.
</p>

<p class="foot">
Monday, August 14, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
How to download an old commit on Bitbucket
</h2>

<p>
I often have this problem, because I am not really skilled at Git, and because
I don't work at big projects, with many contributors. The solution I was looking
for is simply how to download a project as it was in an old commit.
This is pretty easy with Github, because the projects are publicly available, you
simply have to do this:
</p>

<p class="code">
wget https://github.com/{username}/{projectname}/archive/{sha}.zip
</p>

<p>
Then I wanted to do this for my bitbucket project.
There is a download link for each commit, but the projects are private, so we
have to authenticate. One does not have to type the password on
the command line, this is highly not recommended, for security reasons,
it is better to do the following:
</p>

<p class="code">
wget --user=username --ask-password https://bitbucket.org/{owner}/{repository}/get/{sha}.zip
</p>

<p>
All this was learned at StackOverflow: <a href="https://stackoverflow.com/questions/13636559/how-to-download-zip-from-github-for-a-particular-commit-sha">here</a> is the Git reference,
<a href="https://stackoverflow.com/questions/14528344/how-to-access-full-source-of-old-commit-in-bitbucket">
here</a> is the Bitbucket download link reference and
<a href="https://stackoverflow.com/questions/21236004/download-from-bitbucket-authorization-failed">
here</a> is the wget authentication reference.
</p>

<p class="foot">
Sunday, August 13, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Gnuplot Every
</h2>

<p></p>

<p>
Official documentation <a href="http://gnuplot.sourceforge.net/docs_4.2/node121.html">here</a>.
</p>

<p class="foot">
Wednesday, August 9, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Uninstall programs and remove repositories
</h2>

<p>
Resources <br>
https://askubuntu.com/questions/307/how-can-ppas-be-removed <br>
https://askubuntu.com/questions/1143/how-can-i-uninstall-software <br>

</p>

<p class="foot">
Tuesday, August 8, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Linux display manager
</h2>

<p>

</p>

<p>
Resources on this subject are clearly explained <a href="https://askubuntu.com/questions/829108/what-is-gdm3-kdm-lightdm-how-to-install-and-remove-them">here</a>.
</p>

<p class="foot">
Tuesday, August 8, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Terminator shortcuts
</h2>

<p>
Some of the useful shortcuts I use on Terminator are:
</p>

<ul>
<li> Ctrl+Shift+E or Ctrl+Shift+O to split the screen vertically/horizontally </li>
<li> Alt+Arrows to circle through terminals </li>
<li> Ctrl+Shift+X focuses on the currently working terminal </li>
</ul>

<p class="foot">
Tuesday, August 8, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Python 2.7 and Beautiful Soup 4.4
</h2>

<p>
Installed requests
$ pip install requests
installing beautifulsoup4 through pip didn't work, I installed through
apt
$ sudo apt-get install python-bs4
</p>

<p>
References are
<a href="https://www.digitalocean.com/community/tutorials/how-to-scrape-web-pages-with-beautiful-soup-and-python-3">here</a>,
<a href="https://www.digitalocean.com/community/tutorials/how-to-work-with-web-data-using-requests-and-beautiful-soup-with-python-3">here
</a>, and <a href="https://www.crummy.com/software/BeautifulSoup/bs4/doc/">
the official docummentation</a>.
</p>

<p class="foot">
Thursday, August 3, 2017
</p>

</div>
</div><!-- end of blog post-->


<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
An SSH key-based authentication
</h2>

<p>
Set up a new key with
</p>

<p class="code">
$ ssh-keygen
</p>

<p>
Then provide a location (which might be just default) a passphrase to connect. The passphrase
is optional and
is only needed locally, this is one the reasons the key encription is more secure.
Then link this key to the remote server with
</p>

<p class="code">
$ ssh-copy-id username@remote_host
</p>

<p>
Done. You can connect to the remote server the same way as before, with
</p>

<p class="code">
$ ssh username@remote_host
</p>

<p>
This way you can access a remote host, or send files to a web server
without having to type your password every time. There is added security
because the local password might be simple, while the private key
is long and complicated, much more than is humanly possible.
</p>

<p>
To list all ssh keys configured in a computer and
check that you have associated the right keys, just run
</p>

<p class="code">
less ~/.ssh/authorized_keys
</p>

<p>
If you want more details and options, it is all explained in
<a href="https://www.digitalocean.com/community/tutorials/how-to-configure-ssh-key-based-authentication-on-a-linux-server">
this article</a>.
</p>

<p class="foot">
Thursday, August 3, 2017
</p>

</div>
</div><!-- end of blog post-->


<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
VLC shortcuts
</h2>

<p>
This is a list of VLC shortcuts tailored for my needs.
</p>

<ul>
<li> E               frame by frame </li>
<li> F               fullscreen </li>
<li> V               subtitles on/off </li>
<li> Ctrl+Up/Down    volume up/down </li>
<li> Shift+Left/Right    +/- 3 seconds </li>
<li> Alt+Left/Right      +/- 10 seconds </li>
<li> Ctrl+Left/Right     +/- 1 minute </li>
<li> []=                 10% slower/10% faster/normal speed </li>

<p class="foot">
Saturday, July 29, 2017
</p>

</div>
</div><!-- end of blog post-->



<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Film stills
</h2>

<p>
This is just to save the place where I can find great film stills, of classic films,
arranged by title, director, and even cinematographer. The site is <a href="https://film-grab.com/">FilmGrab</a>
</p>

<p>
One more problem solved in Linux. I just don't know if the Spotify Windows user had his problem solved.
</p>

<p>
Recently the problem came back and was harder to solve, I had to delete both preference files,
one of which includes login data:
</p>

<p class="code">
rm ~/.config/spotify/prefs ~/.config/spotify/window_position.prefs
</p>

<p>
It works and resets standard configuration, but after that one has to log in again.
Maybe I can manually alter the prefs file to change window starting position,
and place it where I can minimize/maximize properly. Leave this to a later time.
Another solution is to only remove lines relative to window position, this is also something to try,
remember I have backups for both prefs and window_position, so that the situation can be reversed.
</p>

<p class="foot">
Saturday, July 29, 2017
</p>

</div>
</div><!-- end of blog post-->


<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Problems with Spotify
</h2>

<p>
I had this problem where Spotify was always full screen, even hiding the taskbar, at the bottom
of the screen. I did some research and found <a href="https://community.spotify.com/t5/Desktop-Linux-Windows-Web-Player/Spotify-open-in-full-screen-cannot-access-taskbar-anymore/td-p/1044311">this</a> page reporting the
same problem. Although the OP says he had the problem using Windows 7, the accepted answer
has a strangely linux-looking format, it tells you to remove the "~/.config/spotify/window_position.prefs"
file, then open Spotify again. Indeed, it worked.
</p>

<p>
One more problem solved in Linux. I just don't know if the Spotify Windows user had his problem solved.
</p>

<p class="foot">
Saturday, July 29, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
References on Latex Fonts
</h2>

<p>
<a href="https://tex.stackexchange.com/a/25251/107590">Font families and
selecting font</a>
</p>


<p class="foot">
Wednesday, July 26, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Setting up a backup on Linux
</h2>

<p>
An interesting option to backup a filesystem is
</p>

<p class="code">
$ rsync -av /home/ /media/backup_drive/
</p>

<p>
This is very similar to the command I use to send updates to this page.
</p>

<p>
a is archive, equivalent to -rlptgoD <br>
r is recursive <br>
l copies symlinks as symlinks <br>
p is preserve permissions <br>
t is preserve times <br>
g is preserve group <br>
o is preserver owner <br>
n is a dry run, nothing really happens <br>
--delete clears files that were deleted in the original folder, it doesn't acumulate <br>
z is compress data
</p>

<p>
I added an alias to the ~/.bashrc file to make backup even easier. Just add the line:
</p>

<p class="code">
alias backup="rsync -av /home/ /media/gabriel/.../backup/ --delete"
</p>

<p>
Then all you have to do is run "backup" and the computer will do the task.
Remember to apply the changes to the bashrc with "source ~/.bashrc"
This can be made periodic with cron or anacron, maybe someday I will talk about it.
</p>

<p class="foot">
Tuesday, July 18, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Great Mathematica resource
</h2>

<p>
This time I am here to report on a great place to study more about Mathematica programming.
The <a href="http://www.mathprogramming-intro.org/">book</a> by Leonid Schifrin, extensive
mathematica.stackexchange user, has all the details about programming logics in mathematics.
This is different from procedural programming, and is more oriented to lists and functions,
the book was a great resource on learning about how Mathematica is structured. It also
has great examples, it is very easy to follow the examples alongside with Mathematica,
and verifiy by yourself what the book is saying.
</p>

<p class="foot">
Tuesday, July 18, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Hardware and Graphics Cards on Linux
</h2>

<p>
To find out what is my graphics card, I tried
</p>

<p class="code">
$ lspci -vnn | grep VGA -A 12
</p>

<p>
This command shows all peripherals connected to the computer. VGA looks for
the graphics card line. On my computer, the output was
</p>

<p>
Where the model of the graphics card is Intel Broadwell-U Integrated Graphics [8086:161e]. This is on the line
of the 'VGA compatible controller'. The first number is the manufacturer, the second is the model.
There is also a Kernel driver in use also, but I looked for it in another manner, as we'll see.
</p>

<p>
I knew what is the model of my graphics card and I also wanted to know that graphics card driver is running. Is
it intel or not? I had this question after looking up intel on the web and found out they have open source
software for their graphics cards (not fact checked, but that is what they say). I then run
</p>

<p class="code">
$ lshw -c video
</p>

<p>
lshw is used to show all information on the hardware. In the output there is 'configuration driver',
which says what is the graphics driver in use.
</p>

<p class="foot">
Tuesday, July 18, 2017
</p>

</div>
</div><!-- end of blog post-->


<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Reports on a failure: BB on Linux
</h2>

<p>
I tried to install the security module for Banco do Brasil in Linux. They have an executable,
which you can just download, make executable and run, and also have a .deb package.
From the website, it looks like they showed real interest in doing something that works easily
for Linux. In the past, we had to install Java from Oracle for the bank software to work.
Apparently not anymore, the only problem is that I tried both approaches and none of them
worked.
I should try one more time, but so far BB has failed me on the computer.
</p>


<p class="foot">
Tuesday, July 18, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Using Wolframscripts
</h2>

<p>
Works well
</p>

<p>
References on the subject are <a href="http://blog.wolfram.com/2017/05/17/wolframscript-run-your-code-from-anywhere/">
here</a> and in Wolfram documentation.
</p>




<p class="foot">
Friday, July 14, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Report on Linux Mint 18.2
</h2>

<p>
After many years of continuous linux use and barely none of windows, with some problems in
the middle of the way, here I am with my first full installation of Linux on a computer.
It was a breeze and is flowing very well. Soon I am going to write more about it.
</p>

<p>
Mention how Antergos XFCE was important in the customization process, then I installed
Ubuntu Gnome at UFRJ and had that problem with dual boot. Then mention that I had a
problem at the home computer with virtual box, still not recognized, I bought an
external hd and here I am with Mint Cinnamon.
</p>

<p>
The installation was done on wednesday, july 12. Then final customization was done
on thursday, july 13, and very quickly I had the computer up and running
</p>

<p>
I had a strange problem, my screen was rotated when I turned on the computer.
Nothing happened on the test with the live usb, only when I turn on the computer for the
first time I saw the screen was rotated. Some incompatibility with my laptop which has
this rotating screen thing. The solution I found on the web was:
</p>

<p class="code">
$ gsettings set org.cinnamon.settings-daemon.peripherals.touchscreen orientation-lock  true
</p>

<p>
I don't know what it does, found it <a href="https://github.com/linuxmint/Cinnamon/issues/6059">
here</a>.
</p>




<p class="foot">
Friday, July 14, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Remote Logout
</h2>

<p>
I had a problem with a remote ssh session. A problem I still have to figure out how to solve:
at UFRJ I can log to CTG-dev and leave the computer logged for hours without touching it,
the connection is not lost. Here at home, if I connect to ssh, I have to always do something
at the terminal, or the connection is lost. I don't know if it's some configuration I can
fiddle with, or it is the fact that when at UFRJ the IPs are from the same place, and
that's why connection doesn't fall, I have to investigate that.
</p>

<p>
So the connection was lost and I was still connected, I logged in again and logged out of
the old session remotely, using:
</p>

<p class="code">
$ pkill -9 -t pts/9
</p>

<p>
First run 'tty', it shows what is your current session. Then run 'w', it shows all logged in user
sessions. When I didn't know that I used to run 'last' and it also showed the last sessions,
including the users logged in. 'w' is shorter and to the point.
</p>

<p>
Learned this <a href="https://superuser.com/questions/193168/how-can-i-logout-an-open-remote-ssh-session">
here</a>. StackExchange is always there for the solution.
</p>

<p class="foot">
Friday, July 14, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Checksums
</h2>

<p>
We use checksums to make sure that a file was correctly downloaded,
especially large files, like isos. Or the Mathematica installation.
Linux Mint, for instance, provides the checksum for one of its installation
iso <a href="https://ftp.heanet.ie/mirrors/linuxmint.com/stable/18.2/sha256sum.txt">here</a>.
</p>

<p>
To check the integrity, you can run
</p>

<p class="code">
$ sha256sum -b ...iso
</p>

<p>
The option b reads the iso in binary mode. This is the first time I use this option and
it always worked, so I'm not sure what it did before. Or you may use the -c option
to read the sum from a file and check it. Try this:
</p>

<p class="code">
$ sha256sum --ignore-missing -c ...txt
</p>

<p>
Where the .txt file has a list of checksums. The option --ignore-missing tells the
program to ignore problems if some of the files are missing, because I downloaded only
one of the versions, not all of them.
</p>

<p>
Linux Mint, beginner friendly as always, provides a <a href="https://linuxmint.com/verify.php">
page</a> where this is throughly explained.
</p>

<p class="foot">
Wednesday, July 12, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Convert a series of images to a PDF
</h2>

<p>
If you just took a series of pictures, you can turn them into a single pdf very simply,
with the imagemagick program. If it is not installed, run
</p>

<p class="code">
$ sudo apt-get install imagemagick
</p>

<p>Then, to convert the pictures, use</p>

<p class="code">$ convert image1.jpg image2.png image3.bmp output.pdf</p>

<p>This works with a number of extensions. In particular, if your pictures are named in series, like
page1, page2, page3, etc. You can try</p>

<p class="code">
$ convert page*.jpg output.pdf
</p>

<p>
And it works just fine
</p>

<p>
More on this and a GUI way to do it at <a href="https://itsfoss.com/convert-multiple-images-pdf-ubuntu-1304/">How To Geek</a>.
</p>

<p class="foot">
Monday, July 3, 2017
</p>

</div>
</div><!-- end of blog post-->



<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
How to find out your windows product key
</h2>

<p>
A windows license is expensive and keeping your product key
is something you might need.
You can look it up under the computer (if it is a laptop),
usually close to the battery. But even if it has already
erased, you can find it out using the computer.
</p>

<p>
Open 'Microsoft Powershell' and type
</p>

<p class="code">
(Get-WmiObject -query 'select * from SoftwareLicensingService').OA3xOriginalProductKey
</p>

<p>
If it doesn't work, there is software that does that, like ProduKey,
though I didn't try it. I also don't know what is the Powershell,
how it differs from Run and from the Command Prompt.
</p>

<p>
I found out about this at <a href="https://www.howtogeek.com/206329/how-to-find-your-lost-windows-or-office-product-keys/">How To Geek</a>.
</p>

<p class="foot">
Wednesday, June 28, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>Installing fonts on Ubuntu (and unzip)</h2>

<p>
I downloaded a big file with fonts. An observation is that these font
compressed files are valuable, always keep them for future computers.
To install them, just throw everything in the /usr/local/share/fonts/
folder, like this:
</p>

<p class="code">
$ sudo unzip fonts.zip -d /usr/local/share/fonts
</p>

<p>
This also illustrates how to unzip to a specific folder.
</p>

<p>
The awesome font collection came from <a href="https://www.typewolf.com/google-fonts">Typewolf</a>.
</p>

<p>
Soon after that I tried to install the equally awesome package of
fonts from <a href="http://platowebdesign.com/articles/fonts/">Plato</a>,
but they are in rar format and I didn't know how to unrar from the terminal.
What I did was:
</p>

<p class="code">
$ sudo file-roller plato_fonts.rar
</p>

<p>
And I opened the compressed files manager with super user powers,
so I could extract the files to the proper directory.
After all this I was prepared to rock with my presentations.
</p>

<p>
But to install the Plato Fonts collection, this time I tried
</p>

<p class="code">
$ sudo file-roller plato.rar -e /usr/local/share/fonts/
</p>

<p>
This returns a warning message, but in the end it works fine
</p>

<p class="foot">
Tuesday, June 27, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
What I have learned about web development
</h2>

<p>
Since I started building my website, I have learned much about web development
and I even look critically at webpages in general, especially to webpages of physicists.
I have a blog post on that topic (which I can't link to, because this page
is very static so far, but it should get better in the future.)
</p>

<p>
If you are just beginning, Codecademy is the best place to start. The basic is learning
HTML and CSS to have a page and to build its style. Some bootstrap, if you want your web
page to be responsive (responsive is a tech-savy keyword, means that your page works
on any device: desktop, smartphone, tablet, ipod, projecting screens).
</p>

<p>
If you want interactivity, you'd want to learn some Javascript and jQuery. jQuery is a
Javascript library which makes things easier, because programming in pure Javascript
is a difficult mission.
</p>

<p class="foot">
Monday, June 26, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Overwrite local files on Git Pull
</h2>

<p>
First, a warning. The topic of this post refers to dangerous and not recommended practices. It refers to times
when I was less skilled at Git. Doesn't mean that nowadays I'm a git wizard, only means that I have learned
some safety practices since then.
</p>

<p>
Let's begin with the way I used to do it. When there was a merge conflict, I would simply erase the local
changes with
</p>

<p class="code">
$ git fetch --all <br>
$ git reset --hard origin/master <br>
</p>

<p>
Of course I could only do it because I was the only one fiddling with the files and I knew which version was
the up to date one, and what changes I could discard. Then I learned some git (there's a codecademy course for
that, and numerous tutorials on the web). They showed me I should not pull, instead I should fetch and merge:
</p>

<p class="code">
$ git fetch --all <br>
$ git merge origin/master <br>
</p>

or the lazy and somewhat dangerous version

<p class="code">
$ git fetch --all && git merge origin/master
</p>

<p>
I learned this <a href="https://www.quora.com/How-do-I-force-Git-to-overwrite-local-files-on-pull">here</a>.
</p>

<p class="foot">
Monday, June 26, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Vim display colors of gnuplot
</h2>

<p>
I usually write my gnuplots files with a .gp extension and vim does not recognize it as gnuplot automatically.
To do so, one can type on vim
</p>

<p class="code">
:setf gnuplot
</p>

<p>
To change this permanently, add the following lines to your ~/.vimrc file:
</p>

<p class="code">
" Set the type for the file type and override if file type <br>
" already has detected <br>
au BufRead,BufNewFile *.gp set filetype=gnuplot <br>
</p>

<p>
To learn more, <a href="http://learnvimscriptthehardway.stevelosh.com/">this website</a> has many resources on vim scripts,
from customization (editing the ~/.vimrc file, like we just did), to more complex scripting and package building.
</p>

<p class="foot">
Monday, June 26, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
A video: The Case for Land Art
</h2>

<p>
The Art Assignment channel published this video, <a href="https://www.youtube.com/watch?v=STW0eZDsKVg">
The Case for Land Art</a>, to make us think about the purpose and endeavor of Land Art, a sort of art
form which interacts with the natural world, either by displacing its elements to a gallery environment,
or by making art work directly in the environment.
</p>

<p>
The first instance of Land Art I heard about was A Line Made by Walking, by Richard Long, and it is
mentioned in the video (1:52), this and other works are in the Will Gompertz book, "Isso é arte?".
What Richard Long was walk on a straigth line on grass until his footsteps marked a line on the ground.
When I read about it in the book, I didn't look for the picture, and what I imagined was a curved line,
more like paths in a farm, leading somewhere. This is a more geometric, artsy and detached shape.
The straigth line reminds us that this is only art, and is not leading anywhere, this is not a short
path or a necessary path, this is just a path.
</p>

<p>
It also mentions there is a spectrum of what is Land Art and what is not. This led me to think about
the Inhotim museum, which touches several aspects of contemporary art. For instance, it has several
gardens, and there was another text I read these days which mentioned several artists who
planned gardens. On a grander view, Roberto Burle Marx planned the whole museum, which has a series
of marked (with stones) or unmarked (footsteps only) paths, winding and bifurcating. On a smaller,
more specific view, there is a garden designed by Yayoi Kusama, with several floating sivler balls
on the water.
</p>

<p>
And there is all the art around Inhotim. Some are sculptures, or works of art laid out on the grass,
these are distinctely marked as artworks, and while not detached from their environment, they
are distinct. This is art on the land, but it is not land art. There are several giant pavillions,
which act on a larger scale just like the sculptures. But there is the slide. A huge slide built
on art. There are the brick letters and the names spread on the grass. There is the beam drop,
taking away from the landscapes of the city (concrete) and putting it in the wild, a sea of
concrete and concrete beams.
</p>

<p>
An artist whom, on several occasions in Inhotim, interacts with the land is Olafur Elliason. There
is the kaleidoscope, used for observing the environment. And there is the igloo, it is small and composes
the environment around it with a psychedelic blinking fountain (inside), and a silvery unearthy igloo
on the outside.
</p>

<p>
Throughout all of the Inhotim, there are instances of art interacting with the environment in varied ways,
sometimes more as land art, sometimes less. This only illustrates the wide spectrum of uses artists
can make of their environment. Probably, the great attraction to all audiences produced by Inhotim
is in great part due to the mixture of nature so wide and open which are a rare view in the city,
and man made sites, more common to the sight, but at the same time so strange, so unusual,
so purposeless and useless in their strange shapes and materials.
</p>

<p class="foot">
Saturday, June 25, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
A list of quotes
</h2>

<p>
If it wasn't obvious from a map, you can tell the crater is in America since, like many things America,
it is privately owned. <br>
Lisa Randall, Dark Matter and Dinosaurs
</p>

<p>
In 1980, the group led by Walter and Luiz Alvarez proposed that a big meteoroid had collided with the Earth
and rained down rare earth metals, including iridium
Lisa Randall, Dark Matter and Dinosaurs
</p>

<p>
It had long since come to my attention that people of accomplishments rarely sat back and let things
happen to them. They went out and happened to things. <br>
Leonardo da Vinci
</p>

<p class="foot">
Friday, June 23, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
How to view disk usage
</h2>

<p>Display usage of disk for all partitions, including free space, with</p>

<p class="code">
$ df -h
</p>

<p>
-h means human readable form.
</p>

<p>
And to display size of a single folder, or file, use
</p>

<p class="code">
$ du -sh /path-to-folder/
</p>

<p>One nice trick is how to display size of all folders</p>

<p class="code">
$ du -sh */
</p>

<p>Take a look at the manual entries for df and du for more information.</p>

<p class="foot">
Friday, June 23, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Webpages of Physicists: A collection
</h2>

<p>A list of references and curiosities. I started paying attention to this subject
recently, when I started building my own personal webpage. Some are very good and served
as inspiration. Others are pure html, no css involved. The list is heavily biased
towards field theory and statistical mechanics practitioners.</p>

<ul>
<li><a href="http://www.if.ufrj.br/~rodrigomp/index.html">Rodrigo Pereira, UFPE</a>, has a mountain picture too</li>
<li><a href="http://www-thphys.physics.ox.ac.uk/people/JohnCardy/">John Cardy</a>, an example of pure html,
has a mountain picture</li>
<li><a href="http://www.staff.science.uu.nl/~hooft101/">Gerard t'Hooft</a>, pure html with some gifs</li>
<li><a href="http://physics.weber.edu/schroeder/">Daniel V. Schroeder</a>, has a javascript course and little
css actually used</li>
<li><a href="http://www.ifsc.usp.br/~rpereira/">Rodrigo Pereira, IFSC</a>, a neat and clean page</li>
<li><a href="http://users.physics.harvard.edu/~schwartz/index">Matthew Schwartz</a></li>
<li><a href="http://barabasi.com/">Albert-László Barabasi</a>, top contender so far</li>
<li><a href="http://www.ihes.fr/~duminil/">Hugo Duminil-Copin</a>, mathematician, pretty page</li>

</ul>

<p class="foot">
Wednesday, June 21, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Installation of C libraries in Ubuntu
</h2>

<p>
I downloaded the libraries from their official websites:
<a href="http://www.fftw.org/download.html">FFTW</a>,
<a href="https://www.gnu.org/software/gsl/">GSL</a> and
<a href="http://www.feynarts.de/cuba/">Cuba</a>.
Then unzipped them with
</p>

<p class="code">
$ tar -zxvf file.tar.gz
</p>

<p>
The options stand for eXtract, Verbose and File.
For both packages, then, all I had to do was go to the
folder where they were extracted and run the standard sequence</p>

<p class="code">
$ ./configure <br>
$ make <br>
$ sudo make install <br>
</p>

<p>
Many libraries only need this to be installed and configured properly.
</p>

<p class="foot">
Monday, June 19, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Finding duplicate files
</h2>

<p>
fdupes is a powerful program that looks for duplicate files on your computer even if they have different names.
To search the folders Folder1, Folder2, etc for duplicate files, just run
</p>

<p class="code">
$ fdupes -r Folder1 Folder2 ... >> dupes.log
</p>

<p>
The output might be quite long, this is way I redirected it to a differente file.
The program offers several options, like keeping only the first file and deleting all others,
or you can manually look at the log and decide what to do with the duplicated files.
</p>

<p class="foot">
Monday, June 19, 2017
</p>

</div>
</div><!-- end of blog post-->


<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Customize your command line
</h2>

<p>
The PS1 variables stores the look of you command line prompt, you can take a look at its format,
right now, with</p>

<p class="code">
$ echo $PS1
</p>

<p>
To change this look, I added the following line to the '~/.bashrc' file:
</p>

<p class="code">
$ export PS1="\[\033[1;36m\]\u@\h \[\033[0;36m\]\W > \[$(tput sgr0)\]"
</p>

<p>This way, the terminal will be bold light blue (1;36m) and normal light blue (0;36m), you can choose other colors
and other formats for the terminal.
</p>

<p>References on these colors are available at <a href="http://misc.flogisoft.com/bash/tip_colors_and_formatting">this site</a>, for instance.

<p>There are also <a href="http://bashrcgenerator.com/">bash rc generators</a>, which help you build one.
</p>

<p>
Then make changes permanent with
</p>

<p class="code">
$ source ~/.bashrc
</p>

<p class="foot">
Sunday, June 18, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Always up to date comprehensive list of latex packages
</h2>

<p>
This is a list of the latex packages I have used with a brief description of the solutions they provide
</p>

<p class="code">
\usepackage[brazil]{babel} % portuguese	<br>
\usepackage{color} % color comments	<br>
\usepackage[utf8]{inputenc} <br>
\usepackage{hyperref} <br>
\usepackage{amsmath,amssymb,amsfonts,bm} % mathematics <br>
\usepackage{graphicx} % tikz, include figs <br>
\usepackage{caption,subcaption}
\usepackage[parfill]{parskip} % this makes lines between paragraphs and no indentation <br>
\usepackage[a4paper, total={6in, 8in}]{geometry} <br>
\usepackage{authblk} % for authors and affiliations <br>
\usepackage{verbatim} % for long comments <br>
\usepackage{cite} % for use with BibTex <br>
%\usepackage{epstopdf} % not needed lately, don't know why <br>
\usepackage[colorinlistoftodos]{todonotes} <br>
\usepackage{enumitem} % enumerate with letters, numbers <br>

</p>

<p class="foot">
Sunday, June 18, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Scheduling tasks on Ubuntu
</h2>

<p>
Run 'crontab -e' to open the scheduling and add your jobs in the following format
</p>

<p class="code">
MIN HOUR DOM MON DOW CMD
</p>

<p>
These words mean:<br>
MIN: minute <br>
HOUR: hour <br>
DOM: day of month <br>
MON: month (from 1 to 12) <br>
DOW: day of week (from 0 to 6, 0 is Sunday, on some systems it is 7) <br>
And finally CMD is the command you want to execute at the established time.
</p>

<p>Fill these fields with the appropriate numbers, or a * if the task is to be executed always, that is,
every minute, or every hour. You can use intervals too, like 09-18.</p>

<p>To view your crontabs, use 'crontab -l', this shows the crontabs for the user currently logged in.</p>

<p>You can else set up intervals for the task, thus */10 in the minute field means every 10 minutes.</p>

<p>There are also special keywords which can be used instead of the time assignment, they are: @yearly, @daily, @hourly, @monthly and @reboot.</p>

<p>Nice reference at <a href="http://www.thegeekstuff.com/2009/06/15-practical-crontab-examples">The Geek Stuff</a>.</p>

<p class="foot">
Sunday, June 18, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Tunneling traffic on Firefox
</h2>

<p>
How can I use Firefox as if I were in another computer?
You can log in to a remote computer</p>

<p class="code">
$ ssh user@ip -D 1337
</p>

<p>and '-D 1337' tells ssh to launch a SOCKS server on port 1337 locally.</p>

<p>Then open firefox, close all tabs, and go to Settings (the sandwich on the top right),
look for Preferences -> Advanced and, under Connection, go to Settings.</p>

<p>There, check 'Manual proxy configuration' and the line you need to change is SOCKS host:
change it to 'localhost' and port '1337'.</p>

<p>And you are done</p>

<p>Look up <a href="https://askubuntu.com/questions/469582/how-do-i-set-up-a-local-socks-proxy-that-tunnels-traffic-through-ssh">this question</a> for some details and more ssh options.</p>

<p>When you are done, go back to 'no proxy' on the Connection settings.</p>

<p class="foot">
Saturday, June 17, 2017
</p>

</div>
</div><!-- end of blog post-->

<div class="blog-post">
<div class="col-sm-6 col-sm-offset-3">

<h2>
Burn ISO to a Live USB
</h2>

<p>Download the .iso file, open a terminal and navigate to its folder, then run</p>

<p class="code">
$ sudo -i
</p>

<p>List the partitions on the computer</p>

<p class="code">
# lsblk
</p>

<p>This will show you the name of the partition you want to format as a live USB and
tell you whether it is mounted or not. If it is, remember to unmount it</p>

<p class="code">
# umount /dev/sdb1
</p>

<p>Then comes the burning part</p>

<p class="code">
# dd bs=4M if=myfile.iso of=/dev/sdb && sync
</p>

<p>Notice this is not /sdb1/, but /sdb, simply. When you are done, don't forget to leave root</p>

<p>You may test the installation with a virtual machine, such as qemu. By running</p>

<p class="code">
$ qemu-system-x86_64 -hda /dev/sdb
</p>

<p>Finally, you can clean the USB drive with</p>

<p class="code">
$ wipefs --all /dev/sdx
</p>

<p class="foot">
Friday, June 16, 2017
</p>

</div>
</div><!-- end of blog post-->
