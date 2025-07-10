
# 🧠 LRU Cache Implementation in C++

This project implements an **LRU (Least Recently Used) Cache** in C++ using a combination of a doubly linked list and an unordered map for efficient O(1) access and update operations.

---

## 🔍 What is an LRU Cache?

An **LRU Cache** discards the **least recently used items first** when the cache reaches its limit. It is often used in memory management systems to ensure the most relevant or recently accessed data stays available.

---

## 📂 Features

- ✅ O(1) time complexity for `get` and `insert` operations
- ✅ Uses `unordered_map` and `list` from STL
- ✅ Handles cache eviction automatically when capacity is full
- ✅ Tracks the most recently used item

---

## 🧱 Implementation Details

- **`list<Node>`** maintains the order of usage (front = most recent).
- **`unordered_map<string, list<Node>::iterator>`** provides O(1) lookup of nodes.
- **Custom class `Node`** stores the key-value pair.
- If a key is accessed or updated, it moves to the front of the list.

---

## 🚀 Usage

```cpp
LRUCache lru(3);                     // Create LRU Cache with capacity 3
lru.insertKeyValue("mango", 10);     // Insert key-value pairs
lru.insertKeyValue("apple", 20);
lru.insertKeyValue("banana", 30);

cout << lru.mostRecentKey() << endl; // Outputs: banana

lru.insertKeyValue("mango", 40);
cout << lru.mostRecentKey() << endl; // Outputs: banana because it updates the value only but not used it by accessing data

int* val = lru.getValue("mango");    // Access mango (now most recent)
if(val != NULL) {
    cout << *val << endl;
}

lru.insertKeyValue("guava", 20);     // Evicts least recently used item

if(lru.getValue("apple") == NULL) {
    cout << "apple doesn't exist";
}
```

---

## 🛠️ Requirements

- C++11 or higher
- g++ compiler (or any standard C++ compiler)

---

## 💻 How to Run

```bash
g++ LRU.cpp -o lru_cache
./lru_cache
```

---

## 📌 Example Output

```
banana
banana
Order of Mango 40
apple doesn't exist
```

---

## 📚 Concepts Covered

- STL Containers: `list`, `unordered_map`
- Cache design pattern
- OOP in C++

---

## 📃 License

This project is open source and free to use under the [MIT License](https://opensource.org/licenses/MIT).
