# Project_Learn_Rust

This repo is dedicated to me learning rust and documenting it while I do it. I'm breaking down this "project" into two parts:
 - embedded
 - desktop

Most of the work I do on this repo will be embedded, but rust is a weird language, nahmean? So I'm going to do some general rust programming examples and stick it in a desktop folder for reference. If you've happened upon this repo and plan on using it to learn or maybe as reference, I must warn you that I am not a great programmer. I like firmware and hardware. Anything higher than that is extra, so you might see some of my code and think it sucks. If this is the case, it probably does. Let's go over a few things:

## Rust for embedded? Why?

I'm not going to list the cons of rust, mainly because I'm not knowledgeable enough about the language to do so fairly. I will list some things I like:

### Great Support and Tooling provided by Rust

The cargo package system rust provides is cool, but that's not why I like it. I like it because it eliminates the trouble of manually setting up a bunch of terminals, running openocd/jlink server, running gdb, and connecting via another terminal. This isn't that much work, but rust makes it even easier. It also makes it extremely easy to emulate hardware with different run options.

### The compiler is something entirely different

If you are reading this and haven't done a whole lot of research first, I recommend doing so. I will have some links near the end of this readme. Basically, the way rust devs and engineers describe the rust compiler is like so: "It's like having another programmer there watching your back". This is only kinda true. I'd put it more like this: "It's like having a much better programmer tell you what you're doing wrong while watching your back". The compiler is strict, which means you have to write good code (for the most part) for it to compile. Gone are the days of initializing an array with the wrong macro value by accident and it hard fault with no hint as to what actually went wrong. Rules in C aren't very strict, and I like that; but I also like that Rust is strict. If I am working on critical code, and I can use Rust to achieve my goals with no performance loss and a better chance of the outcome being better, I am going to try it.

### Escape proprietary hell

I am sick of running IDEs for every manufacturer of hardware. Microchip mcus? Atmel Studio. Experimental SiFive hardware? All over the place, but platformio w/code is the most stable imo. STM32? Eclipse clone. Texas Instruments? ... You get the point

I can use the rust toolkit and various HALs to replicate the same workflow across any OS and any computer. This is reason enough for me to get into rust. I can also do this on C, but every time I do it I have to relearn some elses tooling and scripts. I've also looked into making my own (see Project Bare Metal), and while I got it to work, I found that doing it for every MCU that interests me is just too time consuming to do on the side.

### Resources

Rust Embedded Intro: https://rust-embedded.github.io/book/intro/index.html
Rust General Intro: https://doc.rust-lang.org/stable/book/title-page.html
