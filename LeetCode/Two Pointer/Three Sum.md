***
```cpp
vector<vector<int>> threeSum(vector<int>& nums) {
	set<vector<int>> set;
	sort(nums.begin(), nums.end());
	int n = nums.size();

	for (int i = 0; i < n; i++) {
		int j = i + 1;
		int k = n - 1;

		while (k > j) {
			int sum = nums[i] + nums[j] + nums[k];
			if (sum == 0) {
				set.insert({nums[i], nums[j], nums[k]});
				k--;
				j++;
			} else if (sum > 0) {
				k--;
			} else {
				j++;
			}
		}
	}

	vector<vector<int>> output;
	for (auto ans : set) {
		output.push_back(ans);
	}

	return ans;
}

```