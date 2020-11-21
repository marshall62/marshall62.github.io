---
layout: post
title:  "Voice Coding in Python using Talon"
date:   2020-10-01 12:36:57 -0400
categories: jekyll update
---
# Getting started with Voice Coding

This is a learning in public blog that will document my process as I attempt to learn how to code by voice.

I have RSI in both hands.  In order to continue working as a programmer I have to find another way to write code beside typing.   If I can reduce my hours on the keyboard/mouse to something like 15 hours per week, this will make a big difference in symptoms.   If I work more than 25 hours on the keyboard for several weeks at a time, I'm toast.

I've been working on an Ubuntu 20 Workstation and program mostly in Python but also do work with
Javascript and React.  I also have done a lot of Java work but haven't in recent years.   I'd like to continue using Intellij IDEA, PyCharm from JetBrains. I use VS Code a bit for Javascript/React stuff.  I'd like to stay on Ubuntu and would like to avoid spending money on speech recognition software and other hardware until I'm certain this is viable.  Once I know it is, I can imagine using Dragon software and switching to a different OS if necessary.    

I would like a more out-of-the-box solution rather than some homegrown thing like I've seen involving emacs.  I've done lots of programming in emacs but I've come to rely on some of the navigation stuff (e.g. goto definition, list callers) that is only in an IDE.

It looks to me like [Talon](https://talonvoice.com/docs/) is the closest fit because I see it can work without Dragon on Ubuntu.  I've joined their Slack community and I'm looking into getting a quality microphone so I can start trying this out.   They list suggested microphones [here](https://talon.wiki/hardware/#model-recommendations).  I have a Blue Snowball which seems similar to the Blue Yeti Nano in their list, so I'm going to get started with it and see how things go.  

**Task 1:  Get my mic working**

Plug in the mic to USB and test if its working.   I open my sound settings (speaker icon upper right) and see the Input set as Microphone: Blue Snowball and when I speak into it, I see the meter jump indicating the mic is being picked up.  This mic is not very directional so we'll see if its gonna work in the next section.

**Task 2: Install Talon.**

I downloaded the [Talon software for Linux](https://talonvoice.com/dl/latest/talon-linux.tar.xz) from the [main Talon site](https://talonvoice.com/) 

Extracted the archive to a directory and got into a terminal window within the Talon folder and ran `source run.sh` and it's running!  Next I stop the app and download [wav2letter](https://talonvoice.com/dl/talon-w2l-small3-dslm-en_US.zip) which takes a while.
The wav2letter zip is then extracted and I move it into the ~/.talon dir so I have the structure:
```
~/.talon/w2l/en_US/*
~/.talon/user/engines.py
```

  I then followed the instructions for getting some initial scripts into my Talon home dir (~/.talon/user) with `git clone git@github.com:knausj85/knausj_talon.git knausj_talon` 
I then edited the file within modes/sleep_mode.talon so that there is no comment in front of: `<phrase>: skip()`.   


**To run**

I go to where I installed talon and run the app with `source run.sh`.   

I see in upper tray area an icon for Talon and click to see that it is indeed running and its using my Blue Snowball mic.  I then go into a text editor and successfully recite the alphabet!  The alphabet words are posted [here](https://whalequench.club/blog/2019/09/03/learning-to-speak-code.html).   At this point when I say "phrase hello world" I get "he" and some junk so I'm not sure what's wrong.  That will be for another day, but this was a good start.  I've spent no money yet.  I did find that if I say "dictation mode", that I could then say words and talon will input them.  I couldn't get the help commands working (e.g. "help alphabet", "help active") but I can get into command mode and move the cursor around a bit within a text editor and I can pause talon with "talon sleep" and "talon wake" so this is a solid beginning.  The next step will be work inside of PyCharm to see if I can enter a simple snippet of code.

Note:  I hit some bumps along the way because I put things in the wrong place.  When you run the Talon app it produces output to your terminal window.  If you don't see messages about it activating your microphone or using the wav2letter, then you need to investigate whether you've followed instructions correctly or post to the Slack #questions channel (which I did once).  




[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
