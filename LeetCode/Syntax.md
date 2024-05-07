***

#### Vector
```cpp
vector<int> vec(x, y);   // size = x, initial value = y
vec.push_back(3);
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

map.first    // Gets the key
map.second   // Gets the value
map.count(x) // Returns the number of elements (0 or 1)
```


#### Priority Queue
```cpp
priority_queue<int, vector<int>, greater<int>> minHeap;
```