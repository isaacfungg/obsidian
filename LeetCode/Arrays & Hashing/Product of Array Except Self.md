***
```cpp
vector<int> productExceptSelf(vector<int>& nums) {
	int n = nums.size();
	
	vector<int> prefix(n, 1);
	vector<int> suffix(n, 1);
	
	for (int i = 1; i < n; i++) {
		prefix[i] = prefix[i - 1] * nums[i - 1];
	}
	
	for (int i = n - 2; i >= 0; i--) {
		suffix[i] = suffix[i + 1] * nums[i + 1];
	}
	
	vector<int> result(n);
	for (int i = 0; i < n; i++) {
		result[i] = prefix[i] * suffix[i];
	}
	
	return result;
}
```

```cpp
vector<int> productExceptSelf(vector<int>& nums) { 
	int n = nums.size(); 
	vector<int> result(n); 
	result[0] = 1; 
	
	for (int i = 1; i < n; i++) { 
		result[i] = result[i - 1] * nums[i - 1]; 
	} 
	
	int suffix = 1;
	for (int i = n - 2; i >= 0; i--) { 
		suffix *= nums[i + 1]; 
		result[i] *= suffix; 
	} 
	
	return result; 
}
```