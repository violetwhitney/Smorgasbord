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

- Create the **navigation mesh** that will be used by both the agent and the player for pathfinding. 
- Select the floor, go to **Window** → **AI** → **Navigation**, 
- go to the Bake Tab and press the **Bake** button.

![processing-diagram](images/webhook1-12.gif#img-full)

### 2 — Creating A Behavior
- We’ll create a wander behavior for our Agent. 
- Go to the Behavior Bricks menu **Window** → **Behavior Bricks** →**Editor**. That will open the Behavior Bricks Editor.

![processing-diagram](images/webhook1-12.gif#img-full)

- The first step is to create a new behavior tree by clicking the `Create new behavior` button in the upper part of the `Collection` tab and naming it “Wander”.

![processing-diagram](images/webhook1-12.gif#img-full)

- Once the new behavior asset has been saved it will appear in the `Behaviors` list and will be opened as a new tab in the behavior graphical editor, showing an initially empty canvas.

![processing-diagram](images/webhook1-12.gif#img-full)

### 3 — Editing Behavior Parameters
- Make the agent move to a position (-20, 0.5, 20)
- In the canvas for the `Wander` behavior **right-click** to add a new node and choose the action **MoveToPosition** from the drop-down menu. You can type **move** in the search box to quickly find the action.

![processing-diagram](images/webhook1-12.gif#img-full)


- Click the new `MoveToPosition' node → **select** the `Node` tab in the Behavior Bricks inspector.
- This tab shows the properties of the selected node in the canvas. In this case you will find the input parameters, that constitute the information the action needs to know how to proceed.
- Change the dropdown from `CONSTANT` to `BLACKBOARD` and **change** the target name to `wanderTarget`.
- All changes are automatically saved in your project so, once done, you can close the Behavior Bricks editor.

![processing-diagram](images/webhook1-12.gif#img-full)

- Connect the Behavior to the “Agent” Game Object
- **Select** the `Agent` → **click** `Add Component` from the inspector tab → **select** the `Behavior Bricks - Behavior Executor`.

- From the asset folders, look for the `Wander` behavior, **drag and drop** it in the Behavior Executor `Behavior` variable where it says `None (Internal Brick Asset)`. This links the wander behavior to the selected game object and executes the Behavior Bricks script during the runtime.

![processing-diagram](images/webhook1-12.gif#img-full)
![processing-diagram](images/webhook1-12.gif#img-full)

- Under the `Behavior Params` change the values to `(-20, .5, 20)`.

![processing-diagram](images/webhook1-12.gif#img-full)


- Launch your project and you will see the `Agent` moving to the left.
Be aware of the Unity warning “The Enemy game object does not have a Nav Mesh Agent component to navigate. One with default values has been added”. This is due to a missing component in the `Enemy`. Specifically, `MoveToPosition` action uses the scene nav mesh, which requires a nav mesh agent component. Unity automatically adds it on runtime when missing, and warns about that. You can avoid the warning adding that component beforehand yourself.


![processing-diagram](images/webhook1-12.gif#img-full)

### 4 — Composing Behaviors
