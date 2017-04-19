# Waterfall (Physics and Animation Coursework)

In this assignment the primary focus is to put in practice some of the topics covered in class to create 
a valid piece of work that can be incorporated in the big team project (Go Fission). So I decided that I 
wanted to  experiment with waterfall effects and the use of Particle Systems. One of the problems faced 
during the development of this project is that the big project has to be done in Unreal which I don´t have
much  experience with. So apart from doing the project the other challenge will be familiar with the 
application in order to create a good solid work to be used in the other project.

# 1. Waterfall Effect Material

Looking for tutorial and information, the first thing I found was nothing related with physics but an 
effect that simulate a waterfall perfectly. It was the manipulation of a material applied to a mesh. 
The solution was pretty realistic applying a Fresnel and Depth Fade to it.

![Alt text](https://github.com/javolo/Waterfall/blob/master/Content/Screenshots/WaterfallMaterial.JPG "Waterfall Material")

# 2. PUDDLE EFFECT

The second effect I got was a puddle tutorial which create a spot of water in a squared floor that increases
over time following an albedo. That includes a couple of Particle Systems emitters and other Blueprint logic 
to create a really cool effect. 

![Alt text](https://github.com/javolo/Waterfall/blob/master/Content/Screenshots/Puddle.JPG "Puddle")

## 2.1 DROPS EMMITER

The first step in the puddle effect is to create a Drops Emitter. This particle system creates a bunch of drops
like a pipe when it´s leeking. The main features are the spawn rate (totally modifyable depending on how much
you want the puddle to grow), the velocity (that will make drop quicker or not) and how much time they are going
to live.

![Alt text](https://github.com/javolo/Waterfall/blob/master/Content/Screenshots/DropsEmitter.JPG "Drop Particles")

## 2.2 DROPS HITTER

The second step

![Alt text](https://github.com/javolo/Waterfall/blob/master/Content/Screenshots/DropsEmitter.JPG "Hit Particles")

## 2.3 DROPS HITTER

# 3. PARTICLE SYSTEMS

