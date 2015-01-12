---
layout: post
title: Code-In with Wikimedia
---

Last month, I [posted]({% post_url 2014-12-01-google-code-in-and-sugar-labs %}) about the starting of my participation in [Google Code-in](http://www.google-melange.com/gci/homepage/google/gci2014). I introduce Google Code-in in that post so be sure to check it out! Since then, I have decided to switch from [Sugar Labs](https://www.sugarlabs.org/) to [Wikimedia](https://www.wikimedia.org/) for various reasons. Without further adieu, let's get started!

## Wikimedia

For those of you who don't know, Wikimedia is an awesome organization that focused on tons of awesome projects. Their most well known project has to be the ever-so-popular Wikipedia, but they have so many more wonderful projects that you can check out [here](https://www.wikimedia.org/).

## Workflow

To complete a task, here is my current workflow:

1. **Search and signup for a task on the Code-in Melange website:** If you didn't know, Melange is the [open-source software](https://melange.googlesource.com/) that runs Code-in and other contests such [Google's Summer of Code](https://developers.google.com/open-source/soc/?csw=1) (a contest similar to Code-in but for college students). The [Melange Code-in website](http://www.google-melange.com/gci/homepage/google/gci2014) holds your account and all the tasks available to you for specific organizations. In fact, you can find the task I am working on right now (writing this blog post) [here](http://www.google-melange.com/gci/task/view/google/gci2014/5880895395332096) (how meta is that!). Once you find a task you like, claim it and it's off to work! (_If the task is non-programming, I work on it and skip to the last step._)

2. **Observe with Phabricator:** Free and open source, [Phabricator](http://phabricator.org/) is [used by Wikimedia](https://phabricator.wikimedia.org/) to manage their projects. One of the main features is issue and bug tracking. Once I claim a task, I usually check out the Phabricator issue linked in the Melange description. There, I observe the history of the issue and try to dissect what needs to be done to fix it. If clarification is needed, a request for more information or help can be commented on the issue. Next, IRC!

3. **Discuss on IRC:** This is my favorite part of this whole event. I spent most of my IRC time on the `#pywikbot` channel (mentioned later) and the mentors there were incredible! None of my CS friends contribute to open-source, so it is really nice to interact with and look up to somebody who does this type of stuff on a regular basis. They were very nice and open and receptive to any questions I had. They definitely made me feel at-home while I was working on the projects. I **CANNOT** stress enough how awesome these mentors are. I can tell that they try to push me to do my best. Anyways, if I ever need help, this is the first place I go.

4. **Program:** This is the meat of the challenge! I program using [IntelliJ](https://www.jetbrains.com/idea/) using the Python plugin (which is really just [PyCharm](https://www.jetbrains.com/pycharm/)). While I am programming, I am mindful of adhering to the coding style and rules of the project. `flake8` is used to check these conventions. This is a constant battle between adding new code, testing it, discussing on the IRC, and the repetition of these until the task is completed.

5. **Send a Patch to Gerrit:** [Gerrit](https://code.google.com/p/gerrit/) is used to submit patches and do code reviews with git (a version control system). Gerrit uses [git-review](http://www.mediawiki.org/wiki/Gerrit/git-review), a Python commandline tool, to submit patches. Before committing, you must first run `git commit -s` to set it in the correct format. After committing the code with an appropriate commit message, it is time to `git review -R` which submits your code for review (`#pywikibot` channel recieves updates from Phabricator and Gerrit on changes relating to Pywikibot). Next Jekins reviews your format-wise to make sure it matches the conventions of the code. If this passes, you wait for a human to review your code and add comments. After you read the comments, make the neccessary changes and repeat steps 3-4 and then `git commit --amend` and then another `git review -R`. Hopefully at the end, your changes are accepted and merged and pass [TravisCI](https://travis-ci.org/wikimedia/pywikibot-core/).

6. **Mark Done on Melange:** When you are all finished, you are ready to mark your task as done on Melange! After this you wait for somebody to judge your work. If it still needs work, you will be notified and will need to repeat steps 3-5 until satisfactory. Make sure to submit before your task time ends (I had a particularly difficult time with this part `:)`)!

If you follow these steps, you should complete a task with no difficulty at all.

## My Projects

So far, I have completed 5 tasks (4 of which are for Wikimedia). As said earlier, I had a blast doing these and would reccomend to anyone to do this next year. Below are the Wikimedia tasks I have completed thus far.

### Logo For European Hackathon

This was my first task I completed for Wikimedia and had a great time doing it. The objective was to create an SVG logo for this year's European Wikimedia Hackathon, held this year in Lyon, France. For this, I decided on using [Adobe Illustrator](http://www.adobe.com/products/illustrator.html) (which I had purchased previously), however tools like [Inkscape](https://inkscape.org/en/) work perfectly as well. I ended up creating two logos for this task:

![Eiffel Tower European Wikimedia Hackathon](https://upload.wikimedia.org/wikipedia/commons/1/14/European_Wiki_Hackathon_Tower_%28Text_Paths%29.svg)

This Eiffel Tower logo is the first one that I worked on. This logo is influenced heavily by [Wikimedia's logo](http://commons.wikimedia.org/wiki/File:Wikimedia-logo.svg), except it is flipped upside-down, rearranged, and has the Eiffel Tower incorporated into it. The colors taken from both logos are extracted from the Wikimedia logo as well. This one is my favorite of the two, however I unfortunately created this before I learned that the contest would be held in Lyon and not Paris. Oh well.

![Cube European Wikimedia Hackathon](https://upload.wikimedia.org/wikipedia/commons/b/bc/European_Wiki_Hackathon_Cube_%28Text_Paths%29.svg)

Above is the second design I created, focusing on a modern-ish, geometric design. This one was very interesting to make because it was very math-based. The creation consisted of shearing/skewing the objects by certain values and rotating them along 45&deg; angles to create an isomorphic view.

As mentioned earlier, the event is going to be held in Lyon and not Paris, so I might end up creating another logo. This task gave me a general acquaintance with how other wikis, particularly [MediaWiki](https://www.mediawiki.org/wiki/MediaWiki), work.

### Tutorial Video for Phabricator

The next task I worked on was creating a video tutorial showing how to use the previously mentioned Phabricator profile page.

<iframe src="https://commons.wikimedia.org/wiki/File%3APhabricator_User-Page_Screencast.ogg?embedplayer=yes" width="500" height="281.25" frameborder="0" >Phabricator Tutorial</iframe>

What you did not see was the near a million re-takes I had to record to get the video to my liking! The hardest part was not messing up and fitting all of the content into the advised 1 minute length. I captured the video using [Fraps](http://www.fraps.com/), however I would reccomend not using this proprietary software. After recording I converted it into the free [Ogg audio video format](http://en.wikipedia.org/wiki/Ogg) using [VLC](http://www.videolan.org/vlc/index.html).

### Porting Code for Pywikibot

This is the task that pushed me to take the plunge to actually write code for an open-source project (other than my own). For this task, I was assigned to port some code over from `pywikibot-compat` to `pywikibot-core`. Before you get to confused, let me explain. [Pywikibot](http://www.mediawiki.org/wiki/Manual:Pywikibot) is a super awesome Python library to interact with wikis, such as Wikipedia.

**For example:** Let's say you have a wiki all about penguins (we'll call it Pengwiki) and the news just broke that the Emperor Penguin's feet were renamed to 'Royal Flippers'! Oh no! It would take a substantial amount of time to rename all instances of 'foot' or 'feet' in the Emperor Penguin page. However, Pywikibot comes to the rescue! You can easily write a script using the Pywikibot module to do this in a few minutes! This also might accomplished with using an existing script. Other awesome things can done with much ease, such as categorizing all the pictures in the 'Emperor Penguin' category to the 'Royal' category as well.

Other than those silly examples, there are literally millions of use cases for this useful tool. Anyways, `pywikibot-core` is the refactored and updated version of `pywikibot-compat`; `core` solidifies the product significantly as compared to the original `compat` (which is still around for, well, compatibility). I was assigned moving a page generator (think of it like a printer that returns wiki pages for certain queries), specifically `LogpagesPageGenerator`, from `compat` to `core`.

The process I went through to complete the task closely follows my workflow mentioned above (Melange -> Phabricator -> IRC -> Code -> Gerrit -> Done!). Porting the code was very interesting as I had to observe how other pieces of code were ported over and try to emulate and adapt the new code that I was writing accordingly.

### Creating Tests for Pywikibot

Creating good tests is arguably more important than the actual code itself. It insures that the code is working as presumed and will work correctly for the users.

For the tasks with pywikibot, I was assigned to create various unit tests. For creating these, I would think of different situations in which the code would be used and assert the results to those values. To actually test the tests in Python I would use `nosetests`, however `coverage` is also used.

If something did not work as I expected, I investigated further. With the help of `#pywikibot`, we were able to identify many hidden bugs and problems that were not previously known.

## Closing Words

Overall, Wikimedia is a really marvelous group of people that put effort into everything they do and make an effort to help those who need it. The biggest takeaway that I recieved from participating is  learning how organized and fun contributing to open-source projects can be! Unfortunately, I won't be able to participate next year, due to the fact that I will probably be 18 before the contest starts. But hey! I could possibly be a mentor next year! Anyways, I will be sure to keep contributing these awesome projects!

-------------------------

~_Davis Robertson_

_Licensed Under [Creative Commons BY 4.0](http://creativecommons.org/licenses/by/4.0/)._
