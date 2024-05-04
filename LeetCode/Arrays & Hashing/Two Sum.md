```cpp
vector<int> twoSum (vector<int> nums, int target) {
	unordered_map<int> map;
	int size = nums.size();

	for (int i = 0; i < size; i++) {
		map[x] = i;
	}

	for (int i = 0; i < size; i++) {
		int complement = target - nums[i];
		if (map.count(complement) && map[complemnet] != i) {
			return ({i, map[complement]});
		}
	}

	return {};
}
```