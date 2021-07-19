---
layout: post
title: "Colony Development: Needs and Job system prototype complete"
Categories: Colony
---

Welcome to my first development update regarding Colony, I'll be talking about what has been achieved over the last week as well as showing off a small bit of video of the systems at work.

# What is Colony?

If you haven't heard me talk about it. Colony is a 3D settlement building/management game where you have to build up a settlement to house a growing colony while surviving against nature and other people in the wilderness. 

# What's been worked on

So, the last 2 weeks where development has started has been involved in getting core game systems running. The first system I worked on was the need system which is managed entirely on a per colonist level. Needs are defined as UObjects and have a core that handles all the re-usable behaviour such as natural decay as well as spawning a 'need response'. Children of this UObject are used to define specific needs and only function with data overrides.

The other system that has been developed is the task system which is intended to be the driving force behind the AI by giving a structured set of what they can actually do. The task system works on two layers. There is a global layer which stores tasks that every colonist can access such as creating a building or sowing a plant. There is also an individual colonist layer which gives the colonists tasks that are instead to address specific needs such as eating food to sate their hunger need. 

# Enough Talk, lets see it

{% include youtubeplayer.html id="MoWg7ZWwgDo" %}

The video above showcases what has been developed thus far and while it is short shows exactly what I described above. The first thing to note is that in the bottom left you see the colonist information panel with the colonist's name as well as what they are doing. At the start he is seen to be standing around which is one of two states a colonist can take while it is not doing anything. Shortly after you see it start wandering around which is the other idle state. During all this you can see the hunger bar is slowly depleting and when that gets to 20% the hunger need response is created and shortly after you'll see Steve start moving faster towards the food. Upon reaching the food he sits there in an eating state for a few seconds then starts his idle AI again. 

# How does Steve eat?

Tasks can take many different shapes which requires different behaviour and this is all handled on the colonist AI itself for now. For eating, eating is classed as an 'interact with object' task. This means the task holds a reference object for the AI to access and the task manages allocating that resource to itself. The AI can then access the resource for that task (in this case, the big orange) and collect information about how long it needs to interact with it.

![Colony - Interact Information setup: Two Unreal Engine 4 variables, one float named Interact Time set to 3, one string named Interact Verb set to 'Eating...'](/assets/images/projects/colony/1907/interactsetup.png)

This information is entirely data driven and allows me to easily setup any type of interacting with an object with minimal additional code. The only additional code needs to be handled on the object itself where there is a defined framework for world objects to be able to define a 'complete interaction' event themselves. 

![Colony - Interaction Setup, A blueprint graph for a base food class, showing getting the needs system from an actor, checking its valid, calling a find need function on that needs system set to the need 'Hunger', checking the object returned is valid and then modifying the value of that object](/assets/images/projects/colony/1907/completeinteraction.png)

This is an example of completing an interaction based on a 'base food' class. As you can see we get a reference to the actor's hunger need and modify it by 1. A need cannot go over 1 so this is just fully sating the need. 

This is all to show for this development update. As a reminder all this news gets posted to my twitter first so feel free to follow me over on https://twitter.com/WillNobleDev to see small snippets of development as they happen.