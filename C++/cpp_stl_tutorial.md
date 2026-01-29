# C++ STL Complete Tutorial - Organized Content

## Introduction to C++ STL

### What is STL?
- STL (Standard Template Library) provides pre-built containers and algorithms
- Makes coding experience better and faster in C++
- Essential for coding tests, placements, internships, and competitive programming
- Saves time by providing ready-to-use data structures and algorithms

### Why Use STL?
**Example scenarios:**
- **Sorting**: Instead of writing merge sort, quick sort, or heap sort from scratch, use STL's sort function (single line)
- **BFS for graphs**: Instead of implementing queue from scratch, use STL's queue container

### Four Main Parts of STL
1. **Containers** (Most important - main focus)
2. **Algorithms** (Second most important)
3. **Iterators**
4. **Functors** (Used occasionally with containers and algorithms)

---

## 1. CONTAINERS

### 1.1 VECTOR

#### What is a Vector?
- Similar to C++ arrays but **dynamic** in nature
- Arrays have constant size that cannot change at runtime
- Vectors can resize dynamically during runtime (increase or decrease)

#### Creating a Vector
```cpp
#include <vector>
vector<int> v;
```

#### Initial Properties
- Initial size = 0
- Check size: `v.size()`

#### How Vectors Grow in Memory

**Initial state:**
- Size = 0

**After first insertion (push_back(1)):**
- Size = 1
- Data: [1]

**After second insertion (push_back(2)):**
- Creates new vector with **double capacity**
- Copies old data
- Inserts new data
- Size = 2
- Capacity = 2

**After third insertion (push_back(3)):**
- Creates vector with capacity = 4
- Copies old data [1, 2]
- Inserts new element [3]
- Size = 3
- Capacity = 4

#### Size vs Capacity
- **Size**: Number of elements actually stored in the vector
- **Capacity**: Number of elements the vector can currently hold
- Capacity doubles each time vector becomes full
- Check capacity: `v.capacity()`

#### Important Vector Functions

**1. push_back()**
- Inserts element at the end
```cpp
v.push_back(1);
v.push_back(2);
v.push_back(3);
```

**2. emplace_back()**
- Similar to push_back but slightly faster
- Constructs element in-place

**3. Accessing Elements**
```cpp
v[0]           // Access using index
v.at(0)        // Access with bounds checking
v.front()      // First element
v.back()       // Last element
```

**4. pop_back()**
- Removes last element
- Reduces size by 1

**5. insert()**
- Insert at specific position
```cpp
v.insert(v.begin() + 1, value);  // Insert at index 1
```

**6. erase()**
- Remove element(s)
```cpp
v.erase(v.begin() + 1);              // Remove element at index 1
v.erase(v.begin() + 1, v.begin() + 3); // Remove range
```

**7. clear()**
- Removes all elements
- Size becomes 0

**8. empty()**
- Returns true if vector is empty

**9. resize()**
- Change vector size
```cpp
v.resize(10);  // Resize to 10 elements
```

**10. swap()**
- Swap contents of two vectors
```cpp
v1.swap(v2);
```

#### Iterating Through Vector

**Method 1: Index-based**
```cpp
for(int i = 0; i < v.size(); i++) {
    cout << v[i];
}
```

**Method 2: Iterator**
```cpp
for(auto it = v.begin(); it != v.end(); it++) {
    cout << *it;
}
```

**Method 3: Range-based for loop**
```cpp
for(auto element : v) {
    cout << element;
}
```

---

### 1.2 PAIR

#### What is Pair?
- Stores two values together
- Can have different data types

#### Creating and Using Pairs
```cpp
pair<int, int> p1 = {1, 2};
pair<int, string> p2 = {1, "hello"};

// Accessing elements
cout << p1.first;   // 1
cout << p1.second;  // 2

// Nested pairs
pair<int, pair<int, int>> p3 = {1, {2, 3}};
cout << p3.first;           // 1
cout << p3.second.first;    // 2
cout << p3.second.second;   // 3
```

#### Pair in Arrays/Vectors
```cpp
pair<int, int> arr[] = {{1,2}, {3,4}, {5,6}};
vector<pair<int, int>> v;
v.push_back({1, 2});
```

---

### 1.3 LIST

#### What is List?
- Doubly linked list implementation
- Efficient insertion and deletion from both ends
- Similar functions to vector

#### Key Differences from Vector
- **push_front()**: Insert at beginning (O(1))
- **pop_front()**: Remove from beginning (O(1))
- No random access using index operator []

#### List Functions
```cpp
list<int> ls;
ls.push_back(2);      // Add at end
ls.push_front(1);     // Add at beginning
ls.emplace_back(3);
ls.emplace_front(0);
```

---

### 1.4 DEQUE (Double-Ended Queue)

#### What is Deque?
- Similar to vector but allows operations at both ends
- Can push/pop from front and back efficiently

#### Deque Functions
```cpp
deque<int> dq;
dq.push_back(1);      // Add at end
dq.push_front(2);     // Add at beginning
dq.pop_back();        // Remove from end
dq.pop_front();       // Remove from beginning
dq.front();           // First element
dq.back();            // Last element
```

---

### 1.5 STACK

#### What is Stack?
- LIFO (Last In First Out) data structure
- Only top element is accessible

#### Stack Operations
```cpp
stack<int> st;
st.push(1);      // Add element
st.push(2);
st.push(3);
st.top();        // Access top element (3)
st.pop();        // Remove top element
st.size();       // Number of elements
st.empty();      // Check if empty
```

#### Time Complexity
- All operations: O(1)

#### Swapping Stacks
```cpp
stack<int> st1, st2;
st1.swap(st2);
```

---

### 1.6 QUEUE

#### What is Queue?
- FIFO (First In First Out) data structure
- Elements added at back, removed from front

#### Queue Operations
```cpp
queue<int> q;
q.push(1);       // Add at back
q.push(2);
q.front();       // Access front element
q.back();        // Access back element
q.pop();         // Remove front element
q.size();
q.empty();
```

#### Time Complexity
- All operations: O(1)

---

### 1.7 PRIORITY QUEUE

#### What is Priority Queue?
- Elements stored in sorted order
- Maximum element always at top (by default - max heap)
- Implemented using heap data structure

#### Creating Priority Queue
```cpp
// Max heap (default)
priority_queue<int> pq;
pq.push(5);
pq.push(2);
pq.push(8);
pq.top();    // Returns 8 (maximum)

// Min heap
priority_queue<int, vector<int>, greater<int>> pq_min;
pq_min.push(5);
pq_min.push(2);
pq_min.push(8);
pq_min.top();    // Returns 2 (minimum)
```

#### Priority Queue Operations
```cpp
pq.push(element);    // Insert element
pq.top();            // Access top element
pq.pop();            // Remove top element
pq.size();
pq.empty();
```

#### Time Complexity
- Push: O(log n)
- Pop: O(log n)
- Top: O(1)

---

### 1.8 SET

#### What is Set?
- Stores **unique elements** in sorted order
- Implemented using Red-Black Tree (balanced BST)
- No duplicate elements allowed

#### Set Operations
```cpp
set<int> s;
s.insert(1);     // Insert element
s.insert(2);
s.insert(2);     // Duplicate - not inserted
s.insert(3);

// Finding elements
auto it = s.find(2);         // Returns iterator
if(it != s.end()) {
    cout << "Found";
}

// Count occurrences (0 or 1 for set)
int cnt = s.count(2);

// Erase elements
s.erase(2);                  // Erase by value
s.erase(it);                 // Erase by iterator

// Size and empty check
s.size();
s.empty();

// Clear all elements
s.clear();
```

#### Set Functions for Bounds
```cpp
// lower_bound(x): First element >= x
auto it = s.lower_bound(3);

// upper_bound(x): First element > x
auto it = s.upper_bound(3);
```

#### Time Complexity
- Insert: O(log n)
- Find: O(log n)
- Erase: O(log n)
- Lower_bound: O(log n)
- Upper_bound: O(log n)

---

### 1.9 MULTISET

#### What is Multiset?
- Similar to set but allows **duplicate elements**
- Maintains sorted order
- All duplicate elements stored together

#### Multiset Operations
```cpp
multiset<int> ms;
ms.insert(1);
ms.insert(1);    // Duplicate allowed
ms.insert(2);

// Count occurrences
int cnt = ms.count(1);  // Returns 2

// Erase all occurrences
ms.erase(1);            // Removes all 1s

// Erase single occurrence
ms.erase(ms.find(1));   // Removes only one 1
```

#### Time Complexity
- Same as set: O(log n)

---

### 1.10 UNORDERED SET

#### What is Unordered Set?
- Stores unique elements (no duplicates)
- **No particular order** (not sorted)
- Implemented using hash table

#### Unordered Set Operations
```cpp
unordered_set<int> us;
us.insert(1);
us.insert(2);
us.insert(3);

// Same functions as set
us.find(2);
us.erase(2);
us.count(2);
us.size();
us.empty();
```

#### Time Complexity
- Average case: O(1) for all operations
- Worst case: O(n)

#### When to Use?
- Use **unordered_set** when you don't need sorted order (faster)
- Use **set** when you need elements in sorted order

---

### 1.11 MAP

#### What is Map?
- Stores key-value pairs
- Keys are **unique** and stored in **sorted order**
- Implemented using Red-Black Tree

#### Map Operations
```cpp
map<int, int> mp;
map<int, string> mp2;
map<string, int> mp3;

// Inserting elements
mp[1] = 10;          // Key=1, Value=10
mp[2] = 20;
mp.insert({3, 30});
mp.emplace(4, 40);

// Accessing elements
cout << mp[1];       // 10
cout << mp[5];       // Returns 0 (default) if key doesn't exist

// Finding elements
auto it = mp.find(2);
if(it != mp.end()) {
    cout << it->first << " " << it->second;
}

// Checking if key exists
if(mp.count(2)) {
    cout << "Key exists";
}

// Erasing elements
mp.erase(2);         // Erase by key
mp.erase(it);        // Erase by iterator

// Size and empty check
mp.size();
mp.empty();

// Clear all elements
mp.clear();
```

#### Iterating Through Map
```cpp
// Method 1: Iterator
for(auto it = mp.begin(); it != mp.end(); it++) {
    cout << it->first << " " << it->second;
}

// Method 2: Range-based for loop
for(auto p : mp) {
    cout << p.first << " " << p.second;
}

// Method 3: Structured binding (C++17)
for(auto [key, value] : mp) {
    cout << key << " " << value;
}
```

#### Time Complexity
- Insert: O(log n)
- Access: O(log n)
- Find: O(log n)
- Erase: O(log n)

---

### 1.12 MULTIMAP

#### What is Multimap?
- Similar to map but allows **duplicate keys**
- Keys stored in sorted order
- Cannot use [] operator for access

#### Multimap Operations
```cpp
multimap<int, int> mmp;
mmp.insert({1, 10});
mmp.insert({1, 20});  // Duplicate key allowed
mmp.insert({2, 30});

// Find and erase
auto it = mmp.find(1);
mmp.erase(it);        // Erases one occurrence
```

---

### 1.13 UNORDERED MAP

#### What is Unordered Map?
- Stores key-value pairs
- Keys are unique but **not sorted**
- Implemented using hash table

#### Unordered Map Operations
```cpp
unordered_map<int, int> ump;
ump[1] = 10;
ump[2] = 20;

// Same functions as map
ump.find(1);
ump.erase(1);
ump.count(1);
```

#### Time Complexity
- Average case: O(1) for all operations
- Worst case: O(n)

#### When to Use?
- Use **unordered_map** when you don't need sorted keys (faster)
- Use **map** when you need keys in sorted order

---

## 2. ITERATORS

### What are Iterators?
- Used to iterate through containers
- Act like pointers to container elements

### Iterator Types

**1. begin()**: Points to first element
**2. end()**: Points to position after last element
**3. rbegin()**: Reverse iterator to last element
**4. rend()**: Reverse iterator to position before first element

### Using Iterators
```cpp
vector<int> v = {1, 2, 3, 4, 5};

// Forward iteration
for(auto it = v.begin(); it != v.end(); it++) {
    cout << *it;  // Dereference to get value
}

// Reverse iteration
for(auto it = v.rbegin(); it != v.rend(); it++) {
    cout << *it;
}
```

### Iterator Arithmetic
```cpp
auto it = v.begin();
it++;           // Move to next element
it--;           // Move to previous element
it = it + 2;    // Jump 2 positions forward
```

---

## 3. ALGORITHMS

### 3.1 SORTING

#### sort()
- Sorts elements in ascending order
- Uses IntroSort (hybrid of QuickSort, HeapSort, and InsertionSort)

```cpp
vector<int> v = {5, 2, 8, 1, 9};
sort(v.begin(), v.end());  // Ascending order
// Result: {1, 2, 5, 8, 9}

// Descending order
sort(v.begin(), v.end(), greater<int>());
// Result: {9, 8, 5, 2, 1}

// Sort array
int arr[] = {5, 2, 8, 1, 9};
int n = 5;
sort(arr, arr + n);

// Sort partial range
sort(v.begin(), v.begin() + 3);  // Sort first 3 elements
```

#### Time Complexity: O(n log n)

---

### 3.2 CUSTOM COMPARATORS

#### Sorting in Custom Order

**For Pairs (sort by second element):**
```cpp
bool comp(pair<int,int> p1, pair<int,int> p2) {
    if(p1.second < p2.second) return true;
    if(p1.second > p2.second) return false;
    if(p1.first > p2.first) return true;  // If second equal, sort by first descending
    return false;
}

vector<pair<int,int>> v = {{1,2}, {2,1}, {4,1}};
sort(v.begin(), v.end(), comp);
```

**Using Lambda Functions:**
```cpp
sort(v.begin(), v.end(), [](pair<int,int> p1, pair<int,int> p2) {
    return p1.second < p2.second;
});
```

---

### 3.3 REVERSE

#### reverse()
- Reverses elements in range

```cpp
vector<int> v = {1, 2, 3, 4, 5};
reverse(v.begin(), v.end());
// Result: {5, 4, 3, 2, 1}

// Reverse partial range
reverse(v.begin(), v.begin() + 3);
```

#### Time Complexity: O(n)

---

### 3.4 ACCUMULATE

#### accumulate()
- Calculates sum of elements
- Requires `#include <numeric>`

```cpp
vector<int> v = {1, 2, 3, 4, 5};
int sum = accumulate(v.begin(), v.end(), 0);  // Sum = 15

// With initial value
int sum = accumulate(v.begin(), v.end(), 10);  // Sum = 25

// For other operations
int product = accumulate(v.begin(), v.end(), 1, multiplies<int>());
```

---

### 3.5 COUNT

#### count()
- Counts occurrences of element

```cpp
vector<int> v = {1, 2, 2, 3, 2, 4};
int cnt = count(v.begin(), v.end(), 2);  // Returns 3
```

#### Time Complexity: O(n)

---

### 3.6 FIND

#### find()
- Searches for element
- Returns iterator to first occurrence

```cpp
vector<int> v = {1, 2, 3, 4, 5};
auto it = find(v.begin(), v.end(), 3);

if(it != v.end()) {
    cout << "Found at position: " << (it - v.begin());
}
```

#### Time Complexity: O(n)

---

### 3.7 ROTATE

#### rotate()
- Rotates elements in range

```cpp
vector<int> v = {1, 2, 3, 4, 5};
rotate(v.begin(), v.begin() + 2, v.end());
// Result: {3, 4, 5, 1, 2}
```

---

### 3.8 UNIQUE

#### unique()
- Removes consecutive duplicate elements
- **Must sort first** for removing all duplicates

```cpp
vector<int> v = {1, 1, 2, 2, 3, 3, 4};
auto it = unique(v.begin(), v.end());
v.erase(it, v.end());  // Actually remove duplicates
// Result: {1, 2, 3, 4}
```

#### Time Complexity: O(n)

---

### 3.9 NEXT_PERMUTATION & PREV_PERMUTATION

#### next_permutation()
- Generates next lexicographically greater permutation
- Returns false if no next permutation exists

```cpp
string s = "abc";
next_permutation(s.begin(), s.end());
// Result: "acb"
```

#### prev_permutation()
- Generates previous lexicographically smaller permutation

```cpp
string s = "bca";
prev_permutation(s.begin(), s.end());
// Result: "bac"
```

#### Generating All Permutations
```cpp
string s = "abc";
sort(s.begin(), s.end());  // Start with smallest permutation
do {
    cout << s << endl;
} while(next_permutation(s.begin(), s.end()));
```

---

### 3.10 MIN & MAX ELEMENT

#### max_element()
- Finds maximum element
- Returns iterator

```cpp
vector<int> v = {1, 5, 3, 9, 2};
auto it = max_element(v.begin(), v.end());
cout << *it;  // 9
```

#### min_element()
- Finds minimum element

```cpp
auto it = min_element(v.begin(), v.end());
cout << *it;  // 1
```

#### Time Complexity: O(n)

---

### 3.11 BINARY SEARCH

#### binary_search()
- Checks if element exists in sorted range
- Returns boolean (true/false)
- **Container must be sorted**

```cpp
vector<int> v = {1, 2, 3, 4, 5};
bool found = binary_search(v.begin(), v.end(), 3);  // true
bool found = binary_search(v.begin(), v.end(), 10); // false
```

#### Time Complexity: O(log n)

---

### 3.12 LOWER_BOUND & UPPER_BOUND

#### lower_bound()
- Returns iterator to first element >= target
- **Container must be sorted**

```cpp
vector<int> v = {1, 2, 4, 4, 5};
auto it = lower_bound(v.begin(), v.end(), 4);
// Points to first 4 (index 2)
```

#### upper_bound()
- Returns iterator to first element > target

```cpp
auto it = upper_bound(v.begin(), v.end(), 4);
// Points to 5 (index 4)
```

#### Time Complexity: O(log n)

---

### 3.13 OTHER USEFUL FUNCTIONS

#### swap()
- Swaps two values
```cpp
int a = 5, b = 10;
swap(a, b);
// a = 10, b = 5
```

#### min() & max()
- Returns minimum/maximum of two values
```cpp
int minimum = min(5, 10);  // 5
int maximum = max(5, 10);  // 10
```

---

### 3.14 BIT MANIPULATION FUNCTIONS

#### __builtin_popcount()
- Counts set bits (1s) in integer
- **GCC compiler specific**

```cpp
int n = 15;  // Binary: 1111
int count = __builtin_popcount(n);  // Returns 4
```

#### For Different Data Types:
```cpp
long n2 = 15;
int count = __builtin_popcountl(n2);   // long

long long n3 = 15;
int count = __builtin_popcountll(n3);  // long long
```

**Note:** These are compiler-specific and not part of standard C++. Primarily used in competitive programming.

---

## 4. FUNCTORS (Function Objects)

### What are Functors?
- Objects that can be called like functions
- Used with algorithms and containers
- Common functors: `greater<>`, `less<>`, `plus<>`, `minus<>`, `multiplies<>`

### Using Functors
```cpp
// Sorting in descending order
sort(v.begin(), v.end(), greater<int>());

// Min heap priority queue
priority_queue<int, vector<int>, greater<int>> pq;

// Accumulate with multiplication
int product = accumulate(v.begin(), v.end(), 1, multiplies<int>());
```

---

## SUMMARY OF TIME COMPLEXITIES

### Containers
| Container | Insert | Delete | Access | Search |
|-----------|--------|--------|--------|--------|
| Vector | O(1) amortized | O(n) | O(1) | O(n) |
| List | O(1) | O(1) | O(n) | O(n) |
| Deque | O(1) | O(1) | O(1) | O(n) |
| Stack | O(1) | O(1) | O(1) | - |
| Queue | O(1) | O(1) | O(1) | - |
| Priority Queue | O(log n) | O(log n) | O(1) | - |
| Set | O(log n) | O(log n) | O(log n) | O(log n) |
| Multiset | O(log n) | O(log n) | O(log n) | O(log n) |
| Unordered Set | O(1) avg | O(1) avg | O(1) avg | O(1) avg |
| Map | O(log n) | O(log n) | O(log n) | O(log n) |
| Multimap | O(log n) | O(log n) | O(log n) | O(log n) |
| Unordered Map | O(1) avg | O(1) avg | O(1) avg | O(1) avg |

### Algorithms
| Algorithm | Time Complexity |
|-----------|----------------|
| sort() | O(n log n) |
| reverse() | O(n) |
| accumulate() | O(n) |
| count() | O(n) |
| find() | O(n) |
| unique() | O(n) |
| binary_search() | O(log n) |
| lower_bound() | O(log n) |
| upper_bound() | O(log n) |
| next_permutation() | O(n) |
| min_element() | O(n) |
| max_element() | O(n) |

---

## KEY POINTS TO REMEMBER

### When to Use What?

**Need sorted unique elements?** → Use `set`
**Need sorted elements with duplicates?** → Use `multiset`
**Need fast lookup without sorting?** → Use `unordered_set`

**Need key-value pairs sorted by key?** → Use `map`
**Need key-value pairs with duplicate keys?** → Use `multimap`
**Need fast key-value lookup without sorting?** → Use `unordered_map`

**Need LIFO (Last In First Out)?** → Use `stack`
**Need FIFO (First In First Out)?** → Use `queue`
**Need to access max/min element quickly?** → Use `priority_queue`

**Need dynamic array?** → Use `vector`
**Need to insert/delete from both ends?** → Use `deque`
**Need efficient insertion/deletion anywhere?** → Use `list`

### Best Practices

1. **Always use iterators** for traversing containers (more flexible)
2. **Use auto keyword** to avoid writing long type names
3. **Use emplace instead of insert/push** when possible (more efficient)
4. **Sort before using binary_search, lower_bound, upper_bound**
5. **Use unordered containers** when order doesn't matter (better performance)
6. **Reserve capacity for vectors** when size is known beforehand
7. **Use const references** when passing containers to functions

---

## CONCLUSION

This tutorial covered all important C++ STL concepts essential for:
- Competitive programming
- Coding interviews
- Placements and internships
- Day-to-day C++ development

**Topics Covered:**
✓ All major containers (vector, list, deque, stack, queue, priority_queue, set, multiset, map, multimap, etc.)
✓ Important algorithms (sort, binary_search, reverse, accumulate, etc.)
✓ Iterators and their usage
✓ Functors and custom comparators
✓ Time complexities for all operations

The STL significantly reduces coding time and helps write cleaner, more efficient code. Master these concepts for better performance in coding challenges and interviews.

Link: [https://www.youtube.com/watch?v=okhdtEk1iKk](https://www.youtube.com/watch?v=okhdtEk1iKk)