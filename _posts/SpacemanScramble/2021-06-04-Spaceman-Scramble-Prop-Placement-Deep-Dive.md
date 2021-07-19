---
layout: post
title: "Spaceman Scramble: Prop Placement System Evolution"
Category: Spaceman Scramble
excerpt: Looking into the evolution of the Prop Placement System in Spaceman Scramble
---

Today i'll be taking a look at my first released project, 'Spaceman Scramble'. If you don't know what Spaceman Scramble is, you can find more information [here](https://www.willnobledev.co.uk/projects/spacemanscramble). We'll be taking a look at how the prop placement system evolved today.

# The System

So, to start with looking at what our goals for the prop placement system were. We wanted a system where players could select a prop from a randomly generated bunch and then place that prop into the level. I was initially solely responsible for this system and my initial plan was to create a grid based system as a base line following our main inspiration for the game being "Ultimate Chicken Horse" which is a 2D game of similar nature. 

## Version 1

Version 1 of this system was prototyped quickly in a little over a week. The system matched the initial design and included collisiion detecting with other props in the grid. A video of version 1 is available below.

{% include youtubeplayer.html id="_FBaOYe0Iiw" %}

### Feedback

This system worked, however it was a bit unsure. The system used WASD to move, Space & Left Control to move up and down and finally Q & E to rotate left and right. The system felt sluggish and ultimately quite janky. Other developers and a group of testers were given access and ultimately agreed that it did not feel right. It was slow in an actual level to place a prop that was distanced from the starting point and when other player's were present, it became very confusing. There was also a feeling of disorientation where testers couldn't figure out where the start of the map was and where the goal of the map was.

### Solutions

So, with the feedback received, it was time to start looking up solutions. A few solutions were tried including allowing players to hold down a key to keep moving in that direction and hiding other player's props before they placed them. These resulted in marginal improvements however the system was still not very well received. Therefore it was time to start looking ahead to version 2.

## Version 2

Moving forward with version 2, I decided to look at freeing the camera from the grid to give the player more control. This also allowed me to let the player see more of the map so they would be able to find their bearings easier. The resulting system meant the player was able to freely move their prop while deciding where to place it, and could preview where in the grid it would lock to by pressing right click. Then they could confirm their position by pressing left click. This system is visible in the video below.

{% include youtubeplayer.html id="Bp9WpFFwxW4" %}

### Feedback

This system was slightly better received. Testers felt that the system was easier to use as they could move around the map quicker however, locking to the grid still felt janky. Testers were asked whether this was due to in the current version it instantly snapped is what caused the issue. Testers did not feel however that the instant snapping was the problem and that the snapping itself was the issue. 

### Solutions

The feedback showed that there was a crucial problem in the system. Testers did not like being constrained to the grid. However this grid based system is what the entire system was designed around. This resulted in some quite serious design changes being needed to overhaul the system. This is where another programmer on the team came in to help out and he proposed an alternate solution. Using basic collision detection to detect if props were colliding and just letting players fly around in a general zone rather then having to place along that grid. A plan was concepted out and work on Version 3 was started.

## Version 3

Version 3 was now introduced. Version 3 offered the same free cam movement that Version 2 offered however now removed the restriction to lock the prop to the grid. This version had one restriction where props still had to be rotated in 90 degree increments however this was something that was planned to be removed in the next iteration. Version 3 can be seen below.

{% include youtubeplayer.html id="IcOmbnJMNTM" %}

### Feedback

Testers responded very positively to this iteration of the system. The freedom to place a prop wherever was very welcome. Testers felt the main way this iteration caused issues was the restriction to only being able to rotate 90 degrees. However since this was already planned to be addressed, no core issues had arisen and we were free to start polishing the system.

## Version 4

Version 4 was an iteration that featured only the change to the rotation to allow players to rotate a prop along the one axis freely. This can be seen below.

{% include youtubeplayer.html id="C7hX3GeTH30" %}

### Feedback

Testers really liked the increased freedom with the rotation however some feedback felt that it had gone too far. Testers sometimes wanted to roughly align a prop with the rest of the level and having complete freedom ended up making this very difficult. 

### Solutions

We looked at this feedback and wondered how to address this. Some testers loved the freedom however some testers wanted a slight restriction on the freedom. It was decided to play it safe, rotation would be restricted to 5 degree increments to avoid restricting it too much,

## Version 5 - The final version

Version 5 was the version we shipped with our release. This featured the rotations working on 5 degree increments as well as adding a new rotation axis. This is visible below.

{% include youtubeplayer.html id="BpyVyA55eHk" %}

### Feedback

Feedback was all positive, the testers who loved the freedom didn't mind the restriction of 5 degree increments and some actually ended up preferring it. The testers who wanted their to be a slight restriction felt happy with the 5 degree increments as it added a slight level of control and consistency. As a development team, we felt very happy with this iteration and decided that after a few more bug fixes, it was ready to ship. 

# Lessons Learnt

The development of this system was a long journey filled with many mistakes. However the many mistakes allow lessons to be learned which is the most important aspect of a project like this.

After reviewing some of the decisions made and some of the slip ups during the design and development of this system, I learnt the following lessons:

1. Tunnel visioning on one system idea is not good. When a system seems like it could be fundamentally flawed, the system should be reviewed as a whole. Taking a step back to see if there's an alternate solution is something that should never be ruled out.
2. Jumping at the first solution that is thought of is not ideal. Designing a system like this should be done based on multiple ideas, including time to decide which one offers the best chance of success. It can work however is a huge risk to take especially on a major gameplay system such as this one. 
3. Asking for a sanity check from another developer is not a sign of weakness. Getting a good result out of a system is more important then holding onto the pride of being the only one to work on it. Relying on the team is something I will need to make sure I improve on in the future as it is a cause of wasted development time during this project.

# Closing

Thanks for reading through my first deep dive. I hope to do more of these so if you have any feedback regarding this post, pleae feel free to shoot any and all feedback to me at willnoble1709@gmail.com or on twitter @WillNobleDev. Finally, I am still currently looking for jobs in the games industry primarily looking at game designer roles or gameplay programmer roles. I am open to other roles so if you have an offer you feel I may be interested in, please shoot me an email.
