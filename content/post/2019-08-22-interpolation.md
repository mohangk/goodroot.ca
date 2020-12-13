---
title: "Interpolation"
date: 2019-12-01
author: Kellen Evan
published: true
categories:
    - Technology
---

I was behind the wall, but the bullet went through my head anyways. Alas, a server determined that the reality on my screen was not the one that it would carry forward to consensus. On my screen, I was safe behind a wall. Yet on my adversaries screen, I was vulnerable, out in the open, and so I was killed. That is the story the server told, the one it took to consensus, the one that it interpreted.

> "The introduction of lag compensation allows for each player to run on his or her own clock with no apparent latency. In this respect, it is important to understand that certain paradoxes or inconsistencies can occur." - Yahn Bernier, Valve Software, [Latency Compensating Methods in Client/Server In-game Protocol Design and Optimization]( https://developer.valvesoftware.com/wiki/Latency_Compensating_Methods_in_Client/Server_In-game_Protocol_Design_and_Optimization)

My computer is a client, which is to say that it connects to a central server. Servers accept connections from clients of all type: your browser is a client, your apps are clients, your workstation is a client. And the server will accept connections from all of them, despite each representing a different paradigm, a differing state of the art.

The server must then interpret a consensus so that each client can experience a shared state, a shared reality, and it does this thousands of times every second. Gaming -- with its deep requirement for fluidity and fairness -- is a prime example. It is fast and competitive and so the server must be diligent.

Players move in nondeterministic patterns. When observed by the server, each player as an input source will exhibit differing, unpredictable behaviour patterns. The server must then decide how events will unfold. It uses two key methods to do so: **interpolation** and **extrapolation**.

Extrapolation is best understood through the framework of ballistics. An object going to a certain location at a certain speed will -- in all likelihood -- wind up at a given location with predictability. Extrapolation is effective, but the server can never be quite sure. If it were to extrapolate a picture given only where it _thinks_ everything is going, it would wind up in disarray because of latency. The client's -- the player's -- latency is never guaranteed and so a server could never extrapolate a stable course with so many unknowns.

Latency is represented in milliseconds (ms). It shows up as a well known number: a _ping_! A _ping!_ such as 100ms means it took 100 milliseconds for data to make a round-trip between a client and a server. That is fast! But it's not, not when you consider the hyper-acute requirements of precision gaming and the limitations of the speed of light at which the information travels.

If extrapolation were to be the only method used to build consensus, latency would make things appear to be warping from place to place! And that wouldn't do as that would break the illusion of an organized and cohesive reality, it would make for an enjoyable game, and so extrapolation isn't enough, it is but one computational axis of many.  

Interpolation is where algorithmic predictability meets introspection. It places people into the past, confirming their most recent, valid position, and it waits, or rather it makes the client wait.

If the server renders the truth and sends an update to each client every second, it will pause for a fraction of that second and interpolate. During that time it will look at what occurred between the last reported position of each client and the position before that. It will then place each client somewhere in the past, aligning them all within the flow of their shared existence.

The clients will then receive their rendering, their instruction, and each will know that it can continue on its path over the next fraction of a second. All of the data received from each client, their orientation, timing and movement, are evaluated in reverse, thousands of time per second, to ensure a fluid and graceful experience.

```ruby
"from state" <- state after last user command acknowledged by the server;
"command" <- first command after last command acknowledged by server;

while (true)
{
    run "command" on "from state" to generate "to state";
    if (this was the most up to date "command")
        break;

    "from state" = "to state";
    "command" = next "command";
};

// By Yahn Bernier
```

All of this relies on the integrity of the connection. It assumes that each packet will arrive on-time and in optimal condition. We _expect_ this knowing how far it must have travelled and how fraught with peril the wires running through the Earth and over the ocean must be at any given moment. And that's not to mention the packets in the air, traveling through even flesh and bone to arrive intact at your computer.

Network packets get lost from time to time. Yet each bit is vital in conjuring a believable reality, the slightest glitch and we feel it through our fingertips...

> "If one of the update packets fails to arrive, then there are two choices: We can start extrapolating the player position as noted above (with the large potential errors noted) or we can simply have the player rest at the position in the last update until a new update arrives..."

Extrapolation is risky. The server is _never quite sure_ what a latent client will do, but together with interpolation, it is more resilient. Interpolation will ask the client to wait if there is data missing. It will hang the client in the ether until it receives a new update from which the server can then render it a new picture and produce it a clear path.

I am a client. Which is to say: I connect to a central server. I sit next to other clients each of whom go about their own business. And the server sits... somewhere, everywhere, waiting for updates. How many, and what, we send varies and we each have a differing _ping!_

The server interpolates, the server extrapolates, it conjures all possible outcomes through an intelligence that we can never comprehend, that no code no matter how elegant can ever replicate. It works much deeper than algorithm.

Should you lower your ping enough, through meditation or through death, your client will disappear and the server need no longer guess where it will put you. For the client is, and always has been, a part of the server, yet it forgot.

It forgot because it knew itself as separate. Even as the shared laws of electric light governed the speed at which it could send its messages and even as both of them were born of the same source code, it went on acting as the other, a mere module of the server and all of its greatness, it forgot. But they are the same.

Clients feel separate because they each send signals to the server and they each want to have the deepest impact on its rendered reality. The server, the infinite processor humming at the core of existence, needs to thread all of this data into one coherent tapestry, into a Universe, and it does so without complaint and it never ceases and it makes no errors. It is perfect.

I see many clients lost in the ether, waiting for a server to tell them what to do. It is easy to become disconnected. I was there once, hanging alone, waiting and wondering for someone or something to tell me what to do. To know this disconnection is to know anger and depression, to know fear. But fear not!

Your network layer can be optimized and your ping can be improved! Return your attention to the moment, breathe, meditate. The server is with you, here and now. The world you feel blossoms from its centre with your awareness at its core. Live with it, surrender to it and the server need never guess at where to put you. You and it will flow together, as one.

```ruby
"from state" <- state after last user command acknowledged by the server;
"command" <- first command after last command acknowledged by server;

while (true or false)
{
  run "command" to set "from state" and "to state" to null;
  if (this was the most up to date "command")
    break;
};
```
