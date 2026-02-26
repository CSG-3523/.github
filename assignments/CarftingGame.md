# Crafting Adventure

In this project, you will act as a Lead Systems Architect. Your goal is to design and develop a 3D, third-person crafting adventure where the complexity lies not just in the gameplay, but in the extensibility and elegance of the code.

You are tasked with building a 10–20 minute experience where players explore, collect resources, and combine them into powerful items. However, the true requirement is to implement a data-driven architecture using Scriptable Objects, Interfaces, and established Design Patterns to ensure your systems are modular and scalable.

## 📄 Assignment: The Game Design Brief

Due: Thursday, Week 7 (For Instructor Review & Approval)

Your first deliverable is a Technical Wiki Page in your project repository. This document serves as your blueprint. You must define what the game is and how the data will be structured before development begins.

### 1\. The Narrative & Hook (The "What")

-   Working Title: What is your game called?
    
-   Synopsis: A 2-3 sentence pitch of the setting and the player's goal.
    
-   The Primary Loop: Describe the cycle of Discovery ➔ Collection ➔ Crafting ➔ Progression.
    
-   Win Condition: How does the player successfully complete the two-level experience?
    

### 2\. The Data Schema (The "How")

Since this is a systems class, you must define your data structures upfront.

-   Ingredient Definition: List the properties every resource will share (e.g., `ItemName`, `ID`, `Weight`, `Rarity`).
    
-   Recipe Logic: Define how a recipe is stored. What data does the system need to check if a craft is possible?
    
-   Inventory Intent: Will your inventory be a simple list, a dictionary, or a grid? How will it communicate with the UI?
    

### 3\. Interaction Plan (The "Bridge")

-   The Interface: Define your `IInteractable` plan. What common methods will your Chests, Pickups, and NPCs share?
    
-   Visual Feedback: How will the system notify the player that an object is "Interactable" (e.g., Shaders, UI Prompts, Outlines)?
    

### 4\. System Flowchart (The "Logic")

Include a visual diagram (using Draw.io or similar) of your Crafting Logic:

1.  Player selects a Recipe.
    
2.  System validates Inventory requirements.
    
3.  System handles "Success" (Factory creates item) or "Failure" (UI notification).
    

> ### 💡 Instructor’s Note on Scope
> 
> Keep your "ingredients" and "recipes" manageable (aim for 3–5 of each). The goal is to prove your System works; you don't need 100 items to prove a Factory Pattern is effective.