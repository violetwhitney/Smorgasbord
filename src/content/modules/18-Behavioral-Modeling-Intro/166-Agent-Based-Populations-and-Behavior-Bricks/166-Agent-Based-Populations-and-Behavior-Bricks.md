---
moduleid: 166
title: Agent Based Modeling and Behavior Bricks
published: True
slug: agent-absed-modeling-and-behavior-bricks
---

Behavioral Modeling:
===========================================

# Agent Based Modeling and Behavior Bricks
## Module Summary

In this tutorial we will use Behavior Bricks (a plugin for character animation) in Unity to create 2 simple agents: an interactive Player (moved around using mouse clicks), and an Agent that wanders around, and pursues the player when it sees them. We’ll cover the following core concepts:

1. Setting Up Behavior Bricks
2. Creating A Behavior
3. Editing Behavior Parameters
4. Composing Behaviors
5. Conditions & Perceptions


## Conceptual Introduction
Behavior Bricks is a character animation plugin for Unity the gaming engine.
What is quite useful about Behavior Bricks and character animation apps like it, is that it allows us to program behavior of an agent with high level programming. Behavior Bricks uses a node based Visual Programming Language (akin to Grasshopper) to program things like character movement, following, or other actions based on other triggers. This will be particularly useful for understanding how behaviors are related to one another in an agent based model.

![processing-diagram](images/webhook1-12.gif#img-full)


## Tutorial
### 1 — Setting Up Behavior Bricks
- Start a new project 3D
- Get [Behavior Bricks](http://bb.padaonegames.com/doku.php?id=start) from the Unity Asset store.
- Go to **Window** → **Asset Store**
- Click **Search** → and search for **“Behavior Bricks”**


![processing-diagram](images/webhook1-12.gif#img-full)

- Select the pink **Import** → this brings up a list of all of the assets in Behavior Bricks. 
- Select **Import** → this will load Behavior Bricks into your current project

![processing-diagram](images/webhook1-12.gif#img-full)

- To get out of the **Asset Store** click the **Scene tab**. You’ll now see **Behavior Bricks** in your project under the **Assets Folder**.

![processing-diagram](images/webhook1-12.gif#img-full)

- Create a plane **GameObject** →**3D** → **Plane**. 
- Right Click it and Rename it to `Floor`.

![processing-diagram](images/webhook1-12.gif#img-full)

- **Set** the position to `(0, 0, 0)`, and the scale to `(5, 1, 5)` so it covers a bigger area. 
- **Check** the `Static` checkbox near the Game Object name in the Inspector.

![processing-diagram](images/webhook1-12.gif#img-full)

- Move the **main camera** to `(0, 20, -30)`, and set the rotation to `(45, 0, 0)` in order to fit the plane into the view.

![processing-diagram](images/webhook1-12.gif#img-full)

- Create a sphere for the player. 
- Rename it to **Player**, and place it in **(0, 0.5, 0)** so it will be over the floor.

![processing-diagram](images/webhook1-12.gif#img-full)

- Create a cube for the agent. 
- Rename it to `Agent`, and place it in `(20, 0.5, 20)`. It will be quite far away from the player, near the plane limits.

![processing-diagram](images/webhook1-12.gif#img-full)

- Create three new materials, `Green`, `Blue` and `Red` and use them for the **floor**, **player** and **agent** respectively. 
- To create a new material go to **Assets** → **Create** → **Material**. 
- Right click to rename the material `Green`. 
- Use the eyedropper to select a color. Then drag and drop the material to assign it to a game object. 
- To quickly duplicate a material **select it** and use **ctrl+d** (Windows) **cmd+d** (Mac). This is a good time to save.

![processing-diagram](images/webhook1-12.gif#img-full)



