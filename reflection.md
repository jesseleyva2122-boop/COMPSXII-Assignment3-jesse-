# Reflection - Object Simulator Assignment

## 1. How does this assignment demonstrate object-oriented programming concepts in C?

This assignment shows how C can simulate several object-oriented programming ideas even though C does not have classes like Python. The `Character` struct stores data such as the name, health, and level, along with function pointers that act like methods. `Warrior` and `Mage` then build on the base `Character` structure and add their own specialized data. This gives the program a structure that is similar to using classes and subclasses in Python.

## 2. What is the purpose of function pointers in the Character struct?

The function pointers in the `Character` struct allow each character to have its own behavior while using the same basic interface. The `attack` pointer can point to `character_attack`, `warrior_attack`, or `mage_attack`, depending on how the object was initialized. This is important because the code can call `character->attack(character)` without needing a completely different function call for every character type. In this way, function pointers help C imitate methods and dynamic behavior.

## 3. How does composition simulate inheritance?

Warrior and Mage each contain a `Character` called `base` as their first member. This gives both derived types access to the same basic fields and function pointers as a regular Character, while also allowing them to have extra information such as strength or mana. Putting the base structure first also makes it possible to treat a Warrior or Mage as a `Character*` when using the shared interface. This is a manual way of creating some of the behavior that inheritance provides automatically in Python.

## 4. How is polymorphism demonstrated in this program?

Polymorphism is demonstrated by putting the Hero, Warrior, and Mage into an array of `Character*` pointers. The program then loops through the array and calls the same `attack` function on each pointer. Even though the call looks the same, the result is different because each object's function pointer was set during initialization. The Hero performs a basic attack, the Warrior swings a sword, and the Mage uses its mana to cast a fireball.

## 5. What was the most challenging part of the assignment?

The most challenging part was understanding how a `Character*` can be converted back into a `Warrior*` or `Mage*` when the specialized attack function needs access to fields that only exist in the derived structure. The cast works because the `Character` base structure is stored first inside both derived structures. I also had to pay attention to the Mage's mana because the attack changes the object's state each time it is called. This helped me understand that function pointers and structs have to be set up carefully for this design to work correctly.

## 6. How does this compare to inheritance in Python?

Python provides classes, inheritance, method overriding, and object behavior directly through its object-oriented system. In this C program, those features have to be built manually using structs, function pointers, initialization functions, and type casts. C gives the programmer much more direct control over how the data and functions are represented in memory, but that control also means there is more responsibility for making sure the pointers and structure relationships are correct. Overall, the assignment helped show that some high-level Python features can be recreated at a lower level in C, but they require more explicit programming.