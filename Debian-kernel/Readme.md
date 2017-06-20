**How to boot any Puppy linux with official LTS Debian/Ubuntu kernel.**

You must have some experience with Puppy linux frugal install to use this method.

I don't know why Puppy linux needs its own compiled kernel since all other binary packages are from the base distribution
like Ubunt/Debian/Slackware etc.
I didn't get answer to this question [here](http://murga-linux.com/puppy/viewtopic.php?p=957707&sid=834e840c23b67e5e35fd7055f5172b69#957707) so here is my view about this: Puppy doesn't need its own compiled kernel.

There already is option to use the official distro kernel in [woof-ce](https://github.com/puppylinux-woof-CE/woof-CE/commit/d8c8b865cc3ead465fd54fcf9e4d1381958a516e) - Puppy linux building scripts. I will not try to re-work this method and I'm sure
the contributors there are much better experts.

But I will show you how to boot any existing Puppy linux distro using official kernel from Debian-Jessie. Easy to make this
procedure work with any other kernel. All needed is [small mdification in the init script](https://github.com/MintPup/Puppy-Linux/commit/d3dc7735692830e9ed9590893aff7a2efb9bbac9) and including the kernel modules from official Debian initrd.img in Puppy initrd.gz

In the next few days I will explain the steps and I will upload [example kernel module](https://github.com/MintPup/Puppy-Linux/releases/tag/v.1.0) for testing,


![puduan-6.0.0](https://github.com/MintPup/Puppy-Linux/blob/master/Debian-kernel/puduan-6.0.0.jpg?raw=true)

![dpup-wheezy](https://github.com/MintPup/Puppy-Linux/blob/master/Debian-kernel/dpup-wheezy.jpg?raw=true)

![saluki](https://github.com/MintPup/Puppy-Linux/blob/master/Debian-kernel/saluki.jpg?raw=true)
