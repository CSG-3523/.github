# 🎮 Prototype (Rapid): Core Loop Validation

Build your **first playable version** of the game.

This is your **“30 Seconds of Fun”**, a quick, rough prototype evaluating:
 - The **Core Game Loop (Collect ➔ Craft ➔ Progress)**
 - **Player Experience Goals**
   - Does it meet the motivation model for the target audience?

---

## DELIVERABLES

### 1\. Core Gameplay Loop

-   Explore
-   Collect at least **3 resources**
-   Trigger a **crafting-related action** (can be fake)
#
### 2\. Player Controller
-   Third-person movement
-   Camera control
-   Basic collision
  
#
### 3\. Interaction System
-   Press key / click/trigger to interact
-   Include at least:
    -   **3 Collectible** (pickup → disappears)
    -   **3 Interactive Object** (door, crafting station, etc.)
    
#
### 4\. Feedback (Keep it Simple)
-   Player knows when something happens
    -   Visual (text, icon, popup, etc.)
    -   Audio (pickup sound, click, etc.)
      
#
### 5\. Greybox Level
-   Built with simple shapes (no art required)
-   Clear path or layout
-   Has a **start and end goal**

#

> [!WARNING]
> **🚫 What NOT to Build (Yet)**
> 
> Do **NOT** fully implement systems:
> -   Inventory system → use a simple counter
> -   Crafting system → fake it or hard-code it
> -   ScriptableObjects / data systems
> -   Design patterns (Observer, Factory, Singleton)


---

## ⚙️ Technical Requirements

### New Input System
-   Movement input
-   Interaction input

---

## 📦 Submission & Workflow

You are not just submitting a build—you are practicing a **team production pipeline**.

### 1\. 🌿 GitHub Branching Workflow (Required)
Use proper version control practices:
-   Work in **separate branches** (feature branches)
-   Create a branch called: `prototype`
    -   All prototype work should be **merged** to this branch
    -   Keep the `prototype` branch stable and playable
-   Do **NOT** work directly in `main`

### 2\. 🎮 WebGL Build (Required)
-   Create a **WebGL build** of your prototype
-   Upload it to **itch.io**
-   Ensure the game is **playable in the browser**

### 3\. 👥 Itch.io 
- Upload the game to **Itch.io**
- Only one member needs to upload the project
- Assign other members as **admins and collaborators**

### 4\. 🔗 Submit Links

Submit the following:
-   Link to your **itch.io page**
-   Link to your **GitHub repository**

Both links must be working and accessible.

> [!WARNING]
> **Common Mistakes to Avoid**
> -   Uploading a broken WebGL build
> -   Submitting a private or inaccessible repo
> -   Working only in `main` (don’t do this)
> -   One person controlling the itch.io page
>
