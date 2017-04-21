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

The second step is create the effect of sparks when hit the floor. Another particle system is create for that.
This one is a little bit different from the first one as it's uses a curve to set the velocity over life. Other
parameters like velocity and size are set like in the drop emitter.

![Alt text](https://github.com/javolo/Waterfall/blob/master/Content/Screenshots/VelOverLife.JPG "Vel. Over Life")

![Alt text](https://github.com/javolo/Waterfall/blob/master/Content/Screenshots/DropsHitter.JPG "Hit Particles")

## 2.3 PUDDLE

The last step in the process is to create the puddle effect. That was done in different steps

## 2.4 PROBLEMS

The puddle effect works fine but there is a slight problem with the particle emitters. Due to the material used to 
create both emitters it doesn't have the specular element so when the animation is played the drops and splash 
effect are not visible. I have to play with the lights to get them to be visible but due to my lack with experience
with Unreal I didn't get that to work.

# 3. PARTICLE SYSTEMS

To solve the problem of the specularity of the material in the particle emitters I created another couple of particle
system following the Unreal basic tutorials. One create single sparks that can substitute the hit emitter and then I 
created a GPU Sprite Emitter to replace the Drops Emitter. 

## 3.1 SPARKS PARTICLE SYSTEM

This particle system is responsible to replace the splash effect when hits the floor or a rock. Manipulating the
parameters like the velocity, the initial size and the spawn number we can simulate the same effect as before. 
Initially the colour is orange which has nothing to be with waterfall but changing the texture or applying the 
material created in the first section would give us good effect.

![Alt text](https://github.com/javolo/Waterfall/blob/master/Content/Screenshots/Sparks.JPG "Sparks")

## 3.2 GPU SPRITE PARTICLE SYSTEM









