***
```cpp

vector<int> topKFrequent(vector<int>& nums, int k) {
	unordered_map<int, int> counter;

	for (int num : nums) {
		counter[num]++;
	}

	priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> minHeap;
	for (auto& [num, freq] : counter) {
		minHeap.push({freq, num});
		if (minHeap.size() > k) {
			minHeap.pop();
		}
	}

	vector<int> result;
	while (!minHeap.empty()) {
		result.push_back(minHeap.top().second);
		minHeap.pop();
	}

	reverse(result.begin(), result.end());

	return result;
}
```
















```cpp
vector<int> topKFrequent(vector<int> nums, int k) {
	unordered_map<int, int> counter;

	for (int num : nums) {
		counter[num]++;
	}

	priority_queue(pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>>) minHeap;
	for (auto& [num, freq] : counter) {
		minHeap.push({num, freq});
		if (minHeap.size() > k) {
			minHeap.pop();
		}
	}

	vector<int> result;
	while (!minHeap.empty()) {
		result.push_back(minHeap.top().second)
		minHeap.pop();
	}

	reverse(result.begin(), result.end());

	return result;
}
```