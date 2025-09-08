---
layout: post
title: Mid-wit binary search
comments: true
---
I talk to my wife a lot. She is fun. 

On good days she get most of my 5+ level thoughts. Those are, thoughts that are 5 or above on a scale of absolutely idiotic, 0, to thoughts that might change the world, 10. 

7+ thoughts get thrown around to my friend groups to see if they hold water. 

Then ideally I would put 8+ thoughts that have been fleshed out a bit on this blog. Lucky you. 

Well today you are getting a level 4 idea. Somewhere between dim-wit and intelligent idea. 

# Manual binary search
On many occasions I need to debug an issue where a 10,000 line text file is throwing an error. Obviously the error is one specific line.

An intelligent person might pull up the source code, step through the file, and identify the issue.

In most cases, not the first thing I do. I have found great success in manual binary search if you meet the following criteria:

 - The program you are debugging can quickly be run over and over again
 - The program you are debugging can quickly give a pass/fail condition
 - The file is reasonable sized,(less than 20,000 lines)
 - Each line is run through the code once and doesnt depend on other lines.

You meet the criteria? Nice now if you like mid-wit ideas follwo these steps:

1. Duplicate the file, just to preserve the original.
2. Cut (Copy & Delete) half the dup file and save it
3. Run the dup file.
	1. If it errors, go to step 2
	2. If it passes, delete the file and paste the deleted half from your cut command, go to step 2
  
Repeat that until you found the error. This feels like it should take a long time, but its a binary search, therefore fairly efficient. 14 passes will resolve 16,384 lines. 14 passes seems like a lot but that should only be 14 minutes or so, which is almost as long as it takes most dev environments to fully load anything. 

Then you have the exact line the error occured. Likely some eyeballs on it can spot-the-difference.

Bonus: If you want to learn or grow from this experience, spool up your codebase while running through this. Once you find the error line, find the code that broke it and commit some new code!
