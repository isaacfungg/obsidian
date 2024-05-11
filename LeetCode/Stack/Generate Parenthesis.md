```cpp
public:
	vector<string> generateParenthesis(int n) {
		vector<string> result;
		backtrack(result, "", 0, 0, n);

		return result;
	}

private:
	void backtrack(vector<string>& result, string current, int left, int right, int n) {
		if (current.size() == 2 * n) {
			result.push_back(current);
			return;
		}

		if (left < n) {
			backtrack(result, current + "(", left + 1, right, n);
		}

		if (left > right) {
			backtrack(result, current + ")", left, right + 1, n);
		}
	}
```

Idea
* The left number of parenthesis is always >= compared to the right. 
* If  `current.size() == 2 * n` that means that the string is the max size ( *3 "(" and 3 ")"* ) so we push it into the vector
* If `left < n` then that means there are still variations with an additional left parenthesis
* If `left > right` then that means that we are allowed to add a right parenthesis and it will still be valid