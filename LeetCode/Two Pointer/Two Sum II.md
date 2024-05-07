```cpp
vector<int> twoSum(vector<int>& numbers, int target) {
	int start = 0;
	int end = numbers.size() - 1;
	
	while (end >= start) {
		int temp = numbers[start] + numbers[end];
		
		if (temp == target) {
			return {start + 1, end + 1};
		} else if (temp > target) {
			end--;
		} else {
			start++;
		}
	}
	
	return {};
}
```