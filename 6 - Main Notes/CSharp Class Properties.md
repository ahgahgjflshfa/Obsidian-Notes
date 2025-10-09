2025-10-09 08:38

Status: Done

Tags: [[CSharp]], [[Python]], 

---
# Topic
Concept of the properties in C# classes.

---
# Key Takeaways
## 1. Usage
C# properties can provide getter and setter for class member.
For example:

```CSharp
class Person {
	private int _age;
	
	public int Age {
		get {
			return _age;
		}
		set {
			if (value >= 0) {
				_age = value;
			}
		}
	}
}
```
- Private field `_age`: Stores the data, hidden from outside code.
- Property `Age`: Provides safe access. You can read (`person.Age`) or write (`person.Age = 25`), but the setter enforces rules (e.g. no negative ages).

## 2. Why?
It protects data integrity. Without properties, `_age` could be set to invalid values directly. Properties make class variables "logical" by adding control.

## 3. Additional
`private set` makes the property can only be set (written to) from within the same class. Outside code can read the property (via `get`) but cannot modify it.

Example:
```CSharp
public int Age {
	get; private set;
}
```


---
# My Understanding
I found this concept similar to python's `@property` decorator. In Python, you can use `@property` for getter and `@<property_name>.setter` for the setter to control access to an attribute with logic.

Python example:
```python
class Person:
	def __init__(self):
		self.age = 0
	
	@property
	def age(self):
		return self._age
		
	@age.setter
	def age(self, value):
		if value >= 0:
			self._age = value
```
- Key similarity: Both hide the internal variable (`_age`) and provide controlled access via a property/method.
- Difference: C# uses `get` / `set` blocks in the property declaration, while Python uses decorators. The concept of encapsulation is the same.


---
# Reference

