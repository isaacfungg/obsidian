```cpp
bool isAnagram(String s, String t) {
	unordered_map<char, int> count;

	for (auto x : s) {
		count[x]++;
	}

	for (auto x : t) {
		count[x]--;
	}

	for (auto x : count) {
		if (x.second != 0) {
			return false;
		}
	}

	return true;
}
```