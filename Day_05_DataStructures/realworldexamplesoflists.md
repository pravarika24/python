# 📋 Real-World Examples of Lists

Lists are used everywhere in real programs. Here are a few practical examples.

---

## ✅ Example 1: Managing a To-Do List

```python
to_do_list = ["Buy Groceries", "Clean the house", "pay bills"]

# Adding tasks to the list
to_do_list.append("Schedule meeting")
to_do_list.append("Go for a run")

# Removing a completed task
to_do_list.remove("Clean the house")

# Checking if a task is in the list
if "pay bills" in to_do_list:
    print("Don't forget to pay the utility bills")

print("To-Do list remaining:")
for task in to_do_list:
    print(f"- {task}")
```

---

## ✅ Example 2: Organizing Student Grades

Use a list to find the highest marks, lowest marks, and average marks.

```python
grades = [85, 92, 78, 90, 88]

print("Highest marks:", max(grades))
print("Lowest marks:", min(grades))
print("Average marks:", sum(grades) / len(grades))
```

---

## ✅ Example 3: Managing an Inventory

Use a list to manage the inventory in a store.

```python
inventory = ["apples", "bananas", "milk"]

# Adding a new item
inventory.append("bread")

# Removing an item
inventory.remove("bananas")

# Checking if an item is in stock
if "milk" in inventory:
    print("Milk is in stock")

# Printing the inventory
print("Current inventory:")
for item in inventory:
    print(f"- {item}")
```
