2025-10-14 16:22

Status: Working

Tags: [[Angular]],

---
# Topic
Angular @Output() and EventEmitter — Child-to-Parent Communication

---
# Summary
In Angular, `@Output()` and `EventEmitter` are used when a child component needs to send data or trigger events to its parent.

While `@Input()` handles **data flow from parent -> child**, `@Output()` handles the **reverse direction (child -> parent)**.

By declaring and `@Output()` property in the child and binding it to an `EventEmitter`, the child can emit custom events that the parent listens to via standard event binding synta — `(eventName)="handler($event)"`

---
# Key Takeaways
- `@Output` marks a property as an **event emitter** that parents can subscribe to.
- `EventEmitter<T>` is a class that allows **strongly-typed events** (`emit(value: T)`).
- The `event` keyword in the parent template refers to the emitted data from the child.
- Enables **unidirectional communication** and clean component boundaries.
- Keeps parent and child **loosely coupled** — the child just emits; it doesn't know who handles it.

---
# My Understanding


---
# Next Steps


---
# Reference

