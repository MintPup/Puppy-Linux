**How to boot any Puppy linux with official LTS Debian/Ubuntu kernel.**

You must have some experience with Puppy linux frugal install to use this method.

I don't know why Puppy linux needs its own compiled kernel since all other binary packages are from the base distribution
like Ubunt/Debian/Slackware etc.
I didn't get answer to this question [here](http://murga-linux.com/puppy/viewtopic.php?p=957707&sid=834e840c23b67e5e35fd7055f5172b69#957707) so here is my view about this: Puppy doesn't need its own compiled kernel.

There already is option to use the official distro kernel in [woof-ce](https://github.com/puppylinux-woof-CE/woof-CE/commit/d8c8b865cc3ead465fd54fcf9e4d1381958a516e) - Puppy linux building scripts. I will not try to re-work this method and I'm sure
the contributors there are much better experts.

But I will show you how to boot any existing Puppy linux distro using official kernel from Debian-Jessie. Easy to make this
procedure work with any other kernel. All needed is [small modification in the init script](https://github.com/MintPup/Puppy-Linux/commit/d3dc7735692830e9ed9590893aff7a2efb9bbac9) and including the kernel modules from official Debian initrd.img in Puppy initrd.gz

In the next few days I will explain the steps and I will upload [example kernel module](https://github.com/MintPup/Puppy-Linux/releases/tag/v.1.0) for testing. The screenshots below show this same module working well on different Puppy systems.

Puppy linux is unique system (for good or bad). It has special DISTRO_SPECS file inside initrd.gz. This file gives unique names for main squashfs (sfs) module and extra sfs modules like adrv, zdrv, ydrv, fdrv. This makes almost impossible to use the same module on different Puppy without renaming or symlinking the modules according to its own DISTRO_SPECS file. This file makes the procedure I like to explain difficult for new users so experience with frugall installed Puppy linux is a must.

I started with the init script from [Puduan-6.0.0-wmx-alpha1a](http://murga-linux.com/puppy/viewtopic.php?t=107913&sid=834e840c23b67e5e35fd7055f5172b69). Don't take alpha as not yet ready. The system works well and stable and what I actually took from there is only the init script. For my needs it is quite current build from woof-ce and because of musher0's [words of encouragement](http://murga-linux.com/puppy/viewtopic.php?p=957866&sid=834e840c23b67e5e35fd7055f5172b69#957866). Luckily this puppy was complex enough (having included adrv, ydrv, fdrv, zdrv module) to give me the universal solution how to use the same module in any new or old Puppy.

Let's start:
If you have already frugal installed [Puduan-6.0.0-wmx-alpha1a](http://murga-linux.com/puppy/viewtopic.php?t=107913&sid=834e840c23b67e5e35fd7055f5172b69) you will have the following files in your Puppy directory:

**adrv_puduan_6.0.0.sfs**

**fdrv_puduan_6.0.0.sfs** - includes mplayer and mencoder (we will replace this sfs with Debian kernel sfs with the same name. You can load mplayer and mencoder on the fly after booting the system).

**puppy_puduan_6.0.0.sfs** - the main system module.

**ydrv_puduan_6.0.0.sfs**

**zdrv_puduan_6.0.0.sfs** - the Puppy kernel (it will not be loaded/ignored after using the new initrd.gz)

**initrd.gz** - will be replaced with Debian one.

**vmlinuz** - will be replaced with Debian one.

![puduan-6.0.0](https://github.com/MintPup/Puppy-Linux/blob/master/Debian-kernel/puduan-6.0.0.jpg?raw=true)

![dpup-wheezy](https://github.com/MintPup/Puppy-Linux/blob/master/Debian-kernel/dpup-wheezy.jpg?raw=true)

![saluki](https://github.com/MintPup/Puppy-Linux/blob/master/Debian-kernel/saluki.jpg?raw=true)
