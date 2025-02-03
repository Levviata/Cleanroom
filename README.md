# Levviata/Cleanroom
> What is this?

A fork of Cleanroom that I'm currently using as a playground to play with Minecraft with a side of brainstorming.

(nothing here is correct, absolute, or final.
I'm inexperienced, and I'm very prone to errors,
but I need to get there eventually and somehow! I'm open to criticism but kindly don't overdo it.)

## Brainstorm
The Category which stores ideas that are currently being brainstormed,
these ideas aren't 100% formed/sensical sometimes beware!

(I would ideally turn these malformed ideas into proper, formed, ones later on. Can't promise I will though)

### LOD
Parse Minecraft's textures into 3–6 LODs (Level Of Details) then bind them to the block render

#### 3 LODs Example

Imagine we had a texture of 16x16, maybe a grass block, <br />
we would want to downscale (more-so divide) this texture by 2 so that its 8x8, then by 2 again, and boom we have our three levels of details!

> How?

16x16 -> 1st LOD.

8x8   -> 2nd LOD.

4x4   -> 3rd LOD.

3 out of 3 levels of detail!

Then after getting our LODs (from previous cache, more on that below)

Optimally, we would cache the LODs on game boot up (JSON files would work fine?)

------

However, this model could be scaled without problems. Put it, 3 LODs is easier than 12!

## Other
Random references that only make sense to me, not very relevant to the reader as you might expect.

<details><summary>LOD discussion; Vertex Arrays, Distance Horizon, FarPlane2</summary>

```
[1:45 AM]Levviata: Im starting to learn about Minecraft's render pipeline and its so convoluted 💀
[1:45 AM]Rongmario: :doge:
[1:45 AM]Rongmario: what parts
[1:46 AM]Levviata: Well, I've been "analyzing" LOD systems and how it could be implemented into Minecraft 
[1:47 AM]Rongmario: So you went to the deep end first :doge:
[1:47 AM]Levviata: Yes 💀
[1:47 AM]Levviata: Again!
[1:47 AM]Levviata: I got into a habit of theorizing and not applying
[1:47 AM]Levviata: Because "have to do it the proper way"
[1:47 AM]Levviata: :doge: 
[1:49 AM]Rongmario: we have vertex arrays, these describe vertex orders to be drawn

basic lod would probably be to modify these arrays to skip over vertices in order to draw bigger quads
[1:50 AM]Levviata: I think that the concept of LOD in Minecraft is not a great idea in general 
[1:50 AM]Levviata: Because of how shitty chunk loading is?
[1:51 AM]Levviata: no
[1:51 AM]Levviata: World gen?
[1:51 AM]Levviata: I dont know 💀
[1:51 AM]Rongmario: there are also tessellation shaders, these operate on vertices/attributes which i would want to try out when i have time :doge:  https://learnopengl.com/Guest-Articles/2021/Tessellation/Tessellation
[1:51 AM]Rongmario: you can essentially do this step^ on the gpu
[1:52 AM]Rongmario: but you're still sending original vertices to the gpu, as opposed to just sending less in the first place if you did all this on the cpu
[1:52 AM]Rongmario: all you have to do is to force more chunks to be rendered
[1:53 AM]Rongmario: annoying part is having to render blocks at full detail first, then make lod of it
[1:53 AM]Rongmario: or you can just look at what distant horizons, farplane2 have done :doge:
[1:56 AM]Levviata: I did look into Distant horizons and I liked more how they did it, but good grief the project is so complex 
[1:56 AM]Levviata: Farplane2 ehhhhh
[1:56 AM]Levviata: It tanks performance sadly
[1:57 AM]Levviata: Didnt look onto how its done there though so dunno if its "better" or not
[1:59 AM]Levviata: Ohhhhhhhh
[2:00 AM]Levviata: I had a similar idea in mind
```

</details>
