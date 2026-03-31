For each topic below, review your reading for in-depth details.  
---

## **1. Naming Conventions**  
Consistent naming improves readability and maintainability. Follow best practices:  
- **Classes & Methods:** PascalCase (`Player`, `AttackEnemy()`).  
- **Variables:** camelCase for locals, `_camelCase` for private, `PascalCase` for public.  
- **Boolean Naming:** Reflects true/false state (`IsPlayerAlive`).  
- **Namespaces:** Organize code to prevent conflicts.  
#### [Read More on Naming Conventions](https://getcreativetoday.com/GCT-Unity/unity-programming/project-management/namespaces)
---
## **2. Game Loops**  
 **Game Loop vs. Interaction Loop**: The game loop is the core cycle that drives gameplay, ensuring seamless player interaction, decision-making, and feedback, while the interaction loop covers broader player-game system interactions.  
- **Core Game Loop**:  
  - **Decision**: Player makes a choice.  
  - **Game Reaction**: The game processes the choice.  
  - **Feedback**: The game responds to the player.  
  - **Repeat**: The cycle continues until progress is made.  
- **Object Interaction Loops**: Smaller loops control object behavior (e.g., a key’s spawning, collision, and destruction).  
- **Unity and Game Loops**: Unity’s script lifecycle integrates with the game loop through key functions:  
  - **Initialization**: `Awake()`, `Start()` (object setup).  
  - **Main Loop**: `Update()`, `FixedUpdate()` (gameplay execution).  
  - **Final Adjustments**: `LateUpdate()` (camera, animations).  
  - **Cleanup**: `OnDestroy()` (removing objects).  
- **Micro-Loops for Objects**: Every object follows its own lifecycle, reacting to inputs, collisions, and world interactions within the broader game loop. 
#### [Read More on Game Loops](https://getcreativetoday.com/GCT-Unity/game-design/game-science/game-loop)
---

## **3. Script Templates**  
Unity provides default templates for script creation, ensuring standard structure and formatting. 
Key placeholders include:  
- `#SCRIPTNAME#`: Inserts the script file name.  
- `#ROOTNAMESPACEBEGIN#/#ROOTNAMESPACEEND#`: Manages namespaces in Unity.  
#### [Read More on Script Templates](https://getcreativetoday.com/GCT-Unity/unity-programming/programming/script-templates)
---

## **4. SOLID Principles**  
The SOLID principles are fundamental to writing scalable, maintainable, and flexible code.  

### **S - Single Responsibility Principle (SRP)**  
*A class should have only one reason to change.*  

✅ **Good Example:**  
```csharp
public class PlayerDataSaver  
{  
    public void SavePlayerData(Player player)  
    {  
        // Code to save player data  
    }  
}
```
Here, `PlayerDataSaver` only handles saving data rather than handling multiple responsibilities.  

❌ **Bad Example:** (Handles both gameplay logic and saving)  
```csharp
public class Player  
{  
    public void Move() { /* Movement Logic */ }  
    public void SaveData() { /* Saving Logic */ }  
}
```
---

### **O - Open/Closed Principle (OCP)**  
*Classes should be open for extension but closed for modification.*  

✅ **Good Example:** (Extending behavior with inheritance)  
```csharp
public abstract class Enemy  
{  
    public abstract void Attack();  
}

public class Zombie : Enemy  
{  
    public override void Attack() { Console.WriteLine("Zombie bite!"); }  
}

public class Robot : Enemy  
{  
    public override void Attack() { Console.WriteLine("Laser attack!"); }  
}
```
New enemy types can be added without modifying the `Enemy` base class.  

❌ **Bad Example:** (Modifies existing code for every new enemy type)  
```csharp
public class Enemy  
{  
    public void Attack(string type)  
    {  
        if (type == "Zombie") { Console.WriteLine("Zombie bite!"); }  
        else if (type == "Robot") { Console.WriteLine("Laser attack!"); }  
    }  
}
```
---

### **L - Liskov Substitution Principle (LSP)**  
*Derived classes should be substitutable for their base classes without altering behavior.*  

✅ **Good Example:**  
```csharp
public abstract class Bird  
{  
    public abstract void Fly();  
}

public class Sparrow : Bird  
{  
    public override void Fly() { Console.WriteLine("Sparrow flying!"); }  
}
```
A `Sparrow` can be used wherever a `Bird` is expected.  

❌ **Bad Example:** (Breaks LSP because Penguins can’t fly)  
```csharp
public class Penguin : Bird  
{  
    public override void Fly() { throw new NotImplementedException(); }  
}
```
---

### **I - Interface Segregation Principle (ISP)**  
*Clients should not be forced to depend on interfaces they do not use.*  

✅ **Good Example:**  
```csharp
public interface IWorker  
{  
    void Work();  
}

public interface IEater  
{  
    void Eat();  
}

public class Robot : IWorker  
{  
    public void Work() { Console.WriteLine("Robot working!"); }  
}

public class Human : IWorker, IEater  
{  
    public void Work() { Console.WriteLine("Human working!"); }  
    public void Eat() { Console.WriteLine("Human eating!"); }  
}
```
Robot only implements `IWorker`, avoiding unnecessary dependencies.  

❌ **Bad Example:** (Forces Robot to implement `Eat()`, which it doesn't need)  
```csharp
public interface IWorker  
{  
    void Work();  
    void Eat();  
}

public class Robot : IWorker  
{  
    public void Work() { Console.WriteLine("Robot working!"); }  
    public void Eat() { throw new NotImplementedException(); }  
}
```
---

### **D - Dependency Inversion Principle (DIP)**  
*High-level modules should depend on abstractions, not concrete implementations.*  

✅ **Good Example:** (Dependency Injection)  
```csharp
public interface IWeapon  
{  
    void UseWeapon();  
}

public class Sword : IWeapon  
{  
    public void UseWeapon() { Console.WriteLine("Swinging sword!"); }  
}

public class Player  
{  
    private readonly IWeapon _weapon;  

    public Player(IWeapon weapon)  
    {  
        _weapon = weapon;  
    }

    public void Attack()  
    {  
        _weapon.UseWeapon();  
    }  
}

// Usage:
Player player = new Player(new Sword());
player.Attack();
```
The `Player` depends on the `IWeapon` interface, not a specific weapon class, allowing for flexibility.  

❌ **Bad Example:** (Tightly coupled)  
```csharp
public class Player  
{  
    private Sword _sword = new Sword();  

    public void Attack()  
    {  
        _sword.UseWeapon();  
    }  
}
```
This prevents the `Player` class from using different weapon types without modifying it.  

#### Refer to E-Book and [See this video for a quick overview](https://youtu.be/2COJ7hYGkt8?si=JaP6d6p9SVibo9C1)
---

## **5. Abstract Classes & Interfaces**  
- **Abstract Classes:** Provide shared behavior but cannot be instantiated. Useful for base functionality.  
- **Interfaces:** Define a contract for multiple classes to follow without enforcing shared implementation.  

✅ **Abstract Class Example:**  
```csharp
public abstract class Animal  
{  
    public abstract void Speak();  
}

public class Dog : Animal  
{  
    public override void Speak() { Console.WriteLine("Bark!"); }  
}
```

✅ **Interface Example:**  
```csharp
public interface IDamageable  
{  
    void TakeDamage(int amount);  
}

public class Enemy : IDamageable  
{  
    public void TakeDamage(int amount) { Console.WriteLine($"Enemy took {amount} damage!"); }  
}
```
#### Refer to E-Book and [See this video for a quick overview](https://youtu.be/50_qBoKGKxs?si=SRnQvZfyhKCq_wVt)
---

## **6. Singleton Pattern**  
Ensures only one instance of a class exists, commonly used for managing global states like configuration or logging.  

✅ **Good Example:**  
```csharp
public class GameManager  
{  
    private static GameManager _instance;  

    public static GameManager Instance
    {
        get{return _instance;}
     }

     void Awake()
     {
        if (_instance == null)
        {
            _instance = this;
        }
        else if (_instance != this)
        {
            Destroy(gameObject);
        }
     }

}
```
#### [Read More on Script Templates](https://getcreativetoday.com/GCT-Unity/game-systems/design-patterns/creational/singleton)
---

## **7. State Pattern**  
Allows an object’s behavior to change dynamically based on its internal state.  

✅ **Example:**  
```csharp
using System;

public enum PlayerState
{
    Running,
    Jumping,
    Idle,
}

public class Player
{
    private PlayerState _currentState;

    public void SetState(PlayerState state)
    {
       _currentState = state;
    }

    void Start()
    {
      SetState(Idle);
    }
 

    public void PerformAction()
    {
        // Full switch statement for handling all game states
        switch (_currentState)
        {
            case PlayerState.Running:
                Debug.Log("Player is running!");
                break;
            case PlayerState.Jumping:
                Debug.Log("Player is jumping!");
                break;
            case PlayerState.Idle:
                Debug.Log("Player is idle.");
                break;
            default:
                Debug.Log("Unknown state.");
                break;
        }
    }


}


```
#### Refer to E-Book
---

## **8. Observer Pattern**  
Defines a one-to-many relationship where changes in one object notify dependent objects.  

✅ **Example:**  
```csharp
// Event definition
public class Broadcaster: MonoBehaviour
{
    public static event Action EventNotification;

    void Start()
    {
        EventNotification?.Invoke();
    }
}

public class Subscriber : MonoBehaviour
{
    void OnEnable()
    {
        Broadcaster.EventNotification += OnEventNotification;
    }

    void OnDisable()
    {
        Broadcaster.EventNotification -= OnEventNotification;
    }

    void OnEventNotification()
    {
        Debug.Log("When event notification is received, subscriber does the thing");
    }
}

```
#### Refer to E-Book
---
