# Logic Diagrams: System Architecture

In this project, you will design and document the **underlying architecture** of your game using visual logic diagrams. While the player experiences exploration and crafting, you will focus on the **invisible structure**—how systems are organized, how data flows, and how game logic is processed.

Rather than writing code, you will create **clear visual maps** that represent how your game functions as a set of interconnected systems.

---

## What Defines a System Architecture?

A professional game is not built from isolated scripts—it is composed of **modular systems that communicate and work together**. For this project, your diagrams must represent:

-   **Game Loop:** The core cycle of player actions that defines the experience (e.g., Explore → Collect → Craft → Progress).
-   **System Design:** Individual systems that handle specific responsibilities.
-   **Data Flow:** How information moves between systems.
-   **System Communication:** How systems stay decoupled while still interacting (events, managers, interfaces).

Your goal is to make the **logic of your game visible**.

---

## 🏃 The Development Structure

You will not create just one diagram. Instead, you will build a **set of diagrams** that represent your game at different levels of detail:

### Main Game Loop: "The Player Experience"

A high-level diagram that captures the core gameplay loop.

-   Focus on player actions and outcomes
-   Keep it simple and readable
-   Represent the “30 seconds of fun”

#

### System Diagrams: "The Building Blocks"

Each team member is responsible for designing **one core system**.

Your system should be one of the following:

-   Resource Management
-   Inventory
-   Crafting
-   World Interaction
-   Puzzle / Progression

Each system diagram must show:

-   Inputs (player actions, triggers, events)
-   Processes (rules, logic, transformations)
-   Outputs (results, state changes, UI updates)
-   Data structures (how information is stored and accessed)

#

### Overall Architecture: "The Technical Foundation"

A complete diagram that shows how all systems connect.

This diagram should:

-   Represent each system as a module
-   Show how systems communicate with each other
-   Clearly illustrate the flow of data

You are encouraged to structure your architecture using professional **Design Patterns**, such as:

-   Observer (event-driven communication)
-   Singleton (centralized managers)
-   Factory (data-driven object creation)

---

## A. Designing Your System Architecture

Begin by thinking about how your game operates beneath the surface. Consider the following guiding questions:

-   What is the core gameplay loop, and how does it repeat?
-   What systems are required to support this loop?
-   What data does each system need to function?
-   How do systems communicate without becoming tightly coupled?
-   Where do design patterns help organize or simplify your logic?

---
## B. Planning Your Diagrams

To keep your work focused and effective:

-   Break your game into **clear, modular systems**
-   Assign **one system per team member**
-   Ensure all diagrams use **consistent structure and labeling**

Your diagrams should prioritize:

-   Clarity over complexity
-   Logic over visuals
-   Structure over detail

---
## C. Tools and Presentation

You may use any of the following tools:

-   Draw.io (recommended)
-   Figma
-   Miro
-   Hand-drawn (must be neat and clearly scanned)

All diagrams must:

-   Be clearly labeled
-   Use consistent symbols and flow direction
-   Be easy to read and understand

---

## Submit for Review

Submit your logic diagrams via a **wiki page titled System Architecture** within your project. Your instructor will review your diagrams to evaluate how well your system architecture::

-   Represents the core gameplay loop
-   Breaks the game into modular systems
-   Demonstrates clear and logical data flow
-   Uses appropriate design patterns

---

## Reference Your Diagrams

These diagrams are not just a deliverable—they are a **blueprint**.

You will use them to:

-   Guide your implementation during prototyping
-   Refactor your code during the Tech Demo phase
-   Ensure your systems remain organized and scalable

A strong architecture now will make development significantly easier later.
