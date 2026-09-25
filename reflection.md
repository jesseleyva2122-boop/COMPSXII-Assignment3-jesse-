# Reflection - Object Simulator Assignment

## 1. How does this assignment demonstrate object-oriented programming concepts in C?

This assignment shows how C can simulate object-oriented programming even though C does not have classes like Python. The Character struct stores both data and function pointers, while Warrior and Mage build on the base Character by putting it first in their structs.

## 2. What is the purpose of function pointers in the Character struct?

The function pointers act like methods that belong to the Character object. Because the attack pointer can point to different functions, the same attack call can produce different behavior for a regular character, a Warrior, or a Mage.

## 3. How does composition simulate inheritance?

Warrior and Mage each contain a Character as their first member, which gives them all of the base Character data and methods. The extra fields, strength and mana, then give each derived type its own specialized information.

## 4. How is polymorphism demonstrated in this program?

Polymorphism is shown by storing the different character types as Character pointers and calling the same attack function through the base pointer. The function pointer has been changed during initialization, so the correct Warrior or Mage attack runs based on the object.

## 5. What was the most challenging part of the assignment?

The most challenging part was understanding how the Character pointer can be cast back to a Warrior or Mage pointer to access the extra fields. It also took some thought to make sure the base Character was the first member so the pointer conversion works correctly.

## 6. How does this compare to inheritance in Python?

Python handles inheritance and method overriding automatically through its class system, while C requires the programmer to build those features manually with structs, function pointers, and casts. C gives more direct control over memory and how the objects are represented, but it also requires more code and careful pointer handling.
