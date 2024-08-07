***

#### General Functions
```cpp
isalnum('a');    // check if a given character is alphanumeric
tolower('A');    // Turns it to lower
stoi("1");       // Turns strings to number
```
#### Vector
```cpp
vector<int> vec(x, y);   // size = x, initial value = y
vec.push_back(3);
vec.pop_back();     // Remove the last element from the vector
vec.back();    // Returns a reference to the last element in the vector
```
#### Hash Set
```cpp
unordered_set<int> set;

set.insert(1);
set.count(num);
```

#### Hash Map
```cpp
unordered_map<int, int> map;

map[x] = 2;  // Placing items in a map
map.first    // Gets the key
map.second   // Gets the value
map.count(x) // Returns the number of elements (0 or 1)

map.find(x) != map.end() // Checks if something is in the map
```

#### Stack
```cpp
stack<char> x;
x.push(y);
x.pop();
x.empty();
x.top();
```
#### Priority Queue
```cpp
priority_queue<int, vector<int>, greater<int>> minHeap;
```