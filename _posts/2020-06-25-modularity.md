---
layout: post
title:  "Modular Design"
date:   2020-05-09
categories: engineering design
---
WE DON'T FULLY UNDERSTAND how most of the technology in our life actually works. How does your remote change the channel on your television? The engineers among us might say that the button opens an electric switch, which supplies power to a laser. The laser activates a photosensor in your TV receptor, which opens a different switch in your television and eventually turns the whole thing on. But hang on, how does the mechanical button actuate the electric switch in the remote?

There is clearly at least one person who understands how the mechanical button actuates the electric circuit. After all, someone designed the remote! The bottom line is that **we don't need to understand** how the remote works. For our purposes, most technology can be considered a black box that receives inputs and demonstrates outputs. You step on the accelerator in your car, an input, and your car moves forward, an output. You can drive a car without having any idea what is underneath your hood (and many people do!).

Technology is inherently modular - the user interacts with the technology through an **interface**. The functional structure has been **abstracted away** for the user experience. Modular design is powerful. It has empowered us to build V8 trucks, supercomputers and rocket ships.

How would you go about building a rocketship, if you decided to? Personally, I would go and hire someone who had done it before. That person might end up hiring an engines team, a flight computer team, a landing gear team, and so on. The flight computer would need to interact with both the engines and the landing gear, so the flight computer team would create an interface between the computer and the engines. **Interfaces exist between modules**. 