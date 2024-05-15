```cpp
bool searchMatrix(vector<vector<int>>& matrix, int target) {
	int height = matrix.size();
	int width = matrix[0].size();
	int left = 0;
	int right = height * width - 1;

	while (left <= right) {
		int middle = left + (right - left) / 2;
		int temp = matrix[middle / width][matrix % width];

		if (temp == target) {
			return true;
		}

		if (temp > target) {
			right = middle - 1;
		} else {
			left = middle + 1;
		}
	}

	return false;
}
```


* Concept
	* Treat the 2d array like a 1d array using *%*
