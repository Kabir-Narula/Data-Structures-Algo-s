# Python Data Structures Cheat Sheet

## 1. Types of Data Structures in Python
Python supports various data structures, which are categorized into primitive and non-primitive data types.

### 1.1 Python Primitive Data Structures
These store simple data values.

| Type       | Description                                                    | Examples          |
|------------|----------------------------------------------------------------|-------------------|
| **String** | Collection of characters surrounded by single or double quotation marks | `'Alice'`, `"Bob"` |
| **Boolean**| Logical values                                                 | `True`, `False`   |
| **Integer**| Whole number of unlimited length                               | `0`, `-273`       |
| **Float**  | Floating-point decimal                                         | `1.618`, `3.1416` |

### 1.2 Python Built-In Non-Primitive Data Structures
These data structures store values and collections of values.

| Type            | Description                    | Ordered | Allow Duplicates | Mutable | Syntax             | Examples                                      |
|-----------------|--------------------------------|---------|------------------|---------|--------------------|-----------------------------------------------|
| **List**        | Ordered collection             | Yes     | Yes              | Yes     | `[ ]`              | `[1, 2.3, True]`, `['John', 'Doe']`           |
| **Tuple**       | Immutable collection           | Yes     | Yes              | No      | `( )`              | `('age', 22)`, `(7.89, False)`                |
| **Set**         | Unordered, unique collection   | No      | No               | Yes     | `{ }`              | `{6, 4.5}`, `{'nice', True}`                  |
| **Dictionary**  | Map storing key-value pairs    | Yes     | No               | Yes     | `{key: value}`     | `{"FB": "Facebook"}`, `{'name': 'Bob'}`       |

---

## 2. List Operations
### 2.1 Accessing Items in Lists
Given a list: `fruit_list = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]`.

| Command              | Description                                                                 |
|----------------------|-----------------------------------------------------------------------------|
| `fruit_list[1]`      | Get the second item on the list (`'banana'`).                                |
| `fruit_list[-1]`     | Get the last item (`'mango'`).                                               |
| `fruit_list[2:5]`    | Get items from index 2 to 4 (`['cherry', 'orange', 'kiwi']`).                 |
| `fruit_list[:4]`     | Get items up to index 4 (`['apple', 'banana', 'cherry', 'orange']`).          |
| `fruit_list[2:]`     | Get items from index 2 to the end (`['cherry', 'orange', 'kiwi', 'melon', 'mango']`). |
| `fruit_list[-4:-1]`  | Get items from index -4 to -1 (`['orange', 'kiwi', 'melon']`).                |
| `if "apple" in fruit_list: print("Yes, we have 'apple'")` | Check if "apple" is in the list                         |

### 2.2 List Methods
Commands marked with an asterisk (*) also apply to tuples.

| Command          | Description                                       | Usage                                   |
|------------------|---------------------------------------------------|-----------------------------------------|
| `append()`       | Add an element to the end of the list              | `list1.append(element)`                 |
| `clear()`        | Remove all elements from the list                  | `list1.clear()`                         |
| `copy()`         | Return a copy of the list                          | `list1.copy()`                          |
| `count()`*       | Return the count of elements                       | `list1.count(element)`                  |
| `extend()`       | Extend list by appending elements from another list| `list1.extend(list2)`                   |
| `index()`*       | Return the index of the specified value            | `list1.index(element[, start[, end]])`  |
| `insert()`       | Insert an element at a specified position          | `list1.insert(position, element)`       |
| `pop()`          | Remove element at specified position               | `list1.pop([index])`                    |
| `remove()`       | Remove first occurrence of an element              | `list1.remove(element)`                 |
| `reverse()`      | Reverse the order of the list                      | `list1.reverse()`                       |
| `sort()`         | Sort list in ascending order                       | `list1.sort()`                          |
| `+`              | Join two lists                                     | `list3 = list1 + list2`                 |
| `del`            | Delete item from list by index                     | `del list1[index]`                      |

### 2.3 List Comprehension
Simplifies creating a new list based on existing values.

| Command                                            | Description                                |
|----------------------------------------------------|--------------------------------------------|
| `[n for n in range(10) if n < 5]`                  | Numbers less than 5                        |
| `[x for x in fruits if "a" in x]`                  | Items containing 'a'                       |
| `[x.upper() for x in fruits]`                      | Make values uppercase                      |
| `[x + '?' for x in fruits]`                        | Add a question mark to each item           |
| `['hello' for x in fruits]`                        | Set all values to 'hello'                  |
| `[x if x != "banana" else "orange" for x in fruits]` | Replace 'banana' with 'orange'             |

---

## 3. Tuple Operations
### 3.1 Accessing Items in Tuples
Given the tuple `fruits = ("apple", "banana", "cherry")`.

| Command             | Description                                         |
|---------------------|-----------------------------------------------------|
| `"apple" in fruits` | Check if `"apple"` is present.                       |
| `(x, y, z) = fruits`| Tuple unpacking                                     |
| `(a, *_) = fruits`  | Assign remaining values to `_`                       |

### 3.2 Modifying Tuples
Tuples cannot be modified directly, but converting to a list and back is a workaround.

| Initial            | `original = ("apple", "banana", "cherry")`            |
|--------------------|------------------------------------------------------|
| **Addition**       | `tempList = list(original); tempList.append("orange"); newList = tuple(tempList)` |
| **Removal**        | `tempList = list(original); tempList.remove("apple"); newList = tuple(tempList)`  |
| **Change**         | `tempList = list(original); tempList[1] = "kiwi"; newList = tuple(tempList)`      |

---

## 4. Dictionary Operations
### 4.1 Adding Items
| Command                        | Description                    |
|--------------------------------|--------------------------------|
| `meta["GIF"] = "Giphy"`        | Add or update key-value pair   |
| `meta.update(new_dict)`        | Update multiple items          |
| `meta = {**meta, **new_dict}`  | Merge dictionaries             |

### 4.2 Dictionary Methods
| Command       | Description                            | Usage                          |
|---------------|----------------------------------------|--------------------------------|
| `clear()`     | Remove all elements                    | `dict1.clear()`                |
| `copy()`      | Return a copy                          | `dict1.copy()`                 |
| `items()`     | Return a list of tuples                | `dict1.items()`                |
| `keys()`      | Return a list of keys                  | `dict1.keys()`                 |
| `pop()`       | Remove the specified key               | `dict1.pop(key_name)`          |
| `popitem()`   | Remove the last inserted key-value pair| `dict1.popitem()`              |
| `values()`    | Return a list of values                | `dict1.values()`               |

---

## 5. Set Operations
Sets are unordered collections with no duplicate elements.

### 5.1 Mathematical Operations
| Command                    | Description                     | Syntax                   |
|----------------------------|---------------------------------|--------------------------|
| `difference()`             | Get the difference              | `set1 - set2`            |
| `intersection()`           | Get the intersection            | `set1 & set2`            |
| `union()`                  | Get the union                   | `set1 | set2`            |
| `symmetric_difference()`   | Get the symmetric difference    | `set1 ^ set2`            |
| `issubset()`               | Check if subset                 | `set1 <= set2`           |
| `issuperset()`             | Check if superset               | `set1 >= set2`           |
| `isdisjoint()`             | Check if sets have no common items | `set1.isdisjoint(set2)`|

---

## 6. Complexity of Operations
### 6.1 List Operations
| Operation          | Complexity  |
|--------------------|-------------|
| `L.append(item)`   | O(1)        |
| `item in L`        | O(N)        |
| `L.sort()`         | O(N*log(N)) |
| `L.pop()`          | O(1)        |

### 6.2 Dictionary Operations
| Operation          | Complexity  |
|--------------------|-------------|
| `d.clear()`        | O(1)        |
| `d.get()`          | O(1)        |
| `for item in d`    | O(N)        |

### 6.3 Set Operations
| Operation                  | Complexity  |
|----------------------------|-------------|
| `s.add(item)`              | O(1)        |
| `s1 - s2`                  | O(len(s1))  |
| `s1 & s2`                  | O(min(len(s1), len(s2))) |

---
