```cpp
int search(vector<int> nums, int target) {
	int left = 0;
	int right = nums.size() - 1;

	while (left <= right) {
		int middle = left + (right - left) / 2;
		int temp = nums[middle];
		
		if (temp == target) {
			return middle;
		}
		if (temp > target) {
			right = middle - 1;
		} else {
			left = middle + 1;
		}
	}

	return -1;
}
```