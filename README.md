# Tasker
Automating web-based tasks using Termux and Tasker


## Abstract
There are a number of web-based tasks I wish to perform on a daily basis, such
as checking the weather, seeing whether the city is open (and, subsequently,
whether or not I have to go to work), whether it's a payday (so I can change
my alarm from a normal one to a happy, I-just-got-money song), and play some
web games and download content from websites which should be deposited into
a backup system, such as Dropbox.

Afterwards, I want to have this information pushed back to my phone either via
Discord or email message. I have considered seeing if Termux can serve
webpages, but I am afraid that the drain on my phone would not make that
feasible. To do this, I will either use Discord's bot api in a private server,
or I will use Python (with requests-html) or Node.js to create an html email 
and serve it using an email api.

While I am not going to be able to post everything that I do, I will attempt
to post as much as I can within this repo that does not go against ToS's for
different services, out me botting in games that disallow it, or give away
sensitive information. I am hoping that the underlying structure of what I
do here will be helpful to those that choose to do the same.

## Why?

While it is the case that any hosting service such as AWS or Digital Ocean
would be able to do the same or better, my phone will be operational almost
all of the time and on my wireless internet connection on the charger at
night. This means that it can perform these tasks for me during nighttime
hours without any interruptions. Instead of costing me 10$ a month for
largely the same amount of processing power or less, I can leverage what
I already have.


## Tasks

+ Check beta.phila.gov to see if their services are operating 
	+ If it isn't, also check my work's website to see if my office is closed
+ Check to see if it's a payday and change the song to a random happy money song
	+ WeekNum % 2 == 0 && WeekDay == Thursday
+ Play games!
	

## Reporting

I am still not sure whether I want to use Discord, email, Dropbox, or a combination of the three. Most likely, depending on the type of task, I will use a combination.


## Personal Notes:

### Tasker

- ~~Tasker apparently does not like .py files (even ones with proper shebangs), but I'm not sure whether it's a chmod issue or if it's something else. A normal bash file worked, so I might have to create bash veneers that call callable python and node.js files to actually get my webstuff done.~~
	- Tasker can handle Python files just fine, you just have to make sure that your shebang points to your python install as though it's outside of the Termux app looking in. The correct shebang is: `#!/data/data/com.termux/files/usr/bin/env python3`
- I believe that Termux is not able to change settings within my phone's alarm clock app, but I did find a thread on reddit that suggested that I could point the app to a file that Termux can edit. I will have to see whether the alarm clock app can access files in Termux's app folders.
