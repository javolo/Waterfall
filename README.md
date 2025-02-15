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

The last step in the process is to create the puddle effect. That was done in different phases. The first phase 
was to set the amount of water, how the edge of the water area is gonna increase and how to plug this with the 
albedo and the puddle material.

![Alt text](https://github.com/javolo/Waterfall/blob/master/Content/Screenshots/PuddleSet.JPG "Set Puddle")

The second phase was to create small waves that go in accordance with the increase of the puddle. This is going to 
help with the ring effect done in phase 3. In this phase we create also the specular and roughness components of
the final material. The have same structure but one of the input variables have opposite value and the a couple of
linear interpolation to get the right effect.

![Alt text](https://github.com/javolo/Waterfall/blob/master/Content/Screenshots/SmallWaves.JPG "Small Waves")

The last phase of the puddle is the creation of rings around the wet area. This is cool effect and you can create
as many ring as you want, the only thing you have to do is duplicate the code to get one ring and then plug everyting
correctly. We start with a timer variable, joined with the work of increasing the puddle in the first phase and 
few linear interpolation between materials we get a thick ring ring that starts in the centre of the puddle and 
finishes in the edge of it.

![Alt text](https://github.com/javolo/Waterfall/blob/master/Content/Screenshots/Rings.JPG "Small Waves")

## 2.4 PROBLEMS

The puddle effect works fine but there is a slight problem with the particle emitters. Due to the material used to 
create both emitters it doesn't have the specular element so when the animation is played the drops and splash 
effect are not visible. I have to play with the lights to get them to be visible but due to my lack with experience
with Unreal I didn't get that to work. In this step we specify as well the colours we want and will plug that into
the final features of the material.

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

Using the spark particle system as base we wanted to create the waterfaall effect. In this case I created a GPU 
emitter as we want to spawn a great number of particle systems. Using the GPU to do this work will increase the 
end result of the effect without slowing our scene. The main feature to play with has been the size of the 
particles spawn as that will give me the desired effect.

![Alt text](https://github.com/javolo/Waterfall/blob/master/Content/Screenshots/GPUSparks.JPG "GPU Sparks")

# 4. FUTURE WORK

As always there is room for improvement and we can get some work done in the rings effect and manipulate some
of the materials to get the drops working much better. As this work is going to be integrated in a bigger project
the creation of assets and textures can jump in the final result of the different particle systems and effects.


