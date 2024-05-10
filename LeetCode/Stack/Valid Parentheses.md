```cpp
bool isValid(string s) {
	stack<char> st;

	for (auto c : s) {
		if (c == '(' || c == '[' || c == '{') {
			st.push(c);
		} else {
			if (st.empty() ||
			(st.top() == '(' && c != ')') ||
			(st.top() == '[' && c != ']') ||
			(st.top() == '{' && c != '}') 
			) {
				return false;
			}

			st.pop();
		}
	}

	return st.empty();
}
```