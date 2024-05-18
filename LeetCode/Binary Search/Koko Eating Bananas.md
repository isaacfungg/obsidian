***
```cpp
int minEatingSpeed(vector<int>& piles, int h) {
	int left = 1;
	int right = *max_element(piles.begin(), piles.end());
	int ans = -1;

	while (left <= right) {
		int middle = left + (right - left) / 2;
		int hours = getHours(piles, middle);

		if (hours <= h) {
			ans = middle;
			right = middle - 1;
		} else {
			left = middle + 1;
		}
	}

	return ans;
}


long getHours(vecotr<int>& piles, int k) {
	long totalHours = 0;
	for (int x : piles) {
		totalHours += (x / k);
		if (x % k != 0) {
			totalHours++;
		}
	}

	return totalHours;
}
```