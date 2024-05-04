***
```cpp
bool containsDuplicate(vector<int>& nums) {
	unordered_set<int> seen;
	for (int num : nums) {
		if (seen.count(num) > 0) {
			return true;
		}
		seen.insert(num);
	}

	return false;
}
```

