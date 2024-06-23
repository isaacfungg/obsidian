***
* When checking an array to see which number does not appear twice you can use an XOR on all the elements to see what is left over. This works because if there are two of the same numbers then it will just turn to 0.

```cpp
int singleNumber(vector<int>& nums) {
	int ans 0;
	for (auto x: nums)
		ans ^= x;
	return ans;
}
```