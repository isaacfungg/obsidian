***
#### Using Set
```cpp
int longestConsecutive(vector<int>& nums) {
	if (nums.size() == 0) return 0;
	
	unordered_set<int> set;
	for (int num : nums) {
		set.insert(num);
	}

	int maxCount = 1;
	for (int num: nums) {
		if (set.count(num - 1) == 0) {
			int count = 1;

			while (set.count(num + count) > 0) {
				count++;
			}

			maxCount = max(maxCount, count);
		}
	}

	return maxCount;
	
}
```
#### Using Hash map
```cpp
int longestConsecutive(vector<int>& nums) {
	unordered_map<int, bool> map;
	int n = nums.size();
	
	if (n == 0) {
		return 0;
	}
	
	for (int i = 0; i < n; i++) {
		map[nums[i]] = true;
	}
	  
	for (int i = 0; i < n; i++) {
		if (map.count(nums[i] - 1) > 0) {
			map[nums[i]] = false;
		}
	}
	
	int maxCount = 1;
	for (int i = 0; i < n; i++) {
		if (map[nums[i]]) {
			int j = 1;
			int count = 1;
			while (map.count(nums[i] + j) > 0) {
				j++;
				count++;
			}
			
			maxCount = max(count, maxCount);
		}
	}
	
	return maxCount;
}
```


