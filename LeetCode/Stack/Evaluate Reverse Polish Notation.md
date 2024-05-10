```cpp
int evalRPN(vector<string>& tokens) {
	stack<int> s;
	for (auto x: tokens) {
		if (x == "+" || x == "-" || x == "*" || x == "/") {
			int num2 = st.top(); st.pop();
			int num1 = st.top(); st.pop();
			int result;

			if (x == "+") result = num1 + num2;
			else if (x == "-") result = num1 - num2;
			else if (x == "*") result = num1 * num2;
			else if (x == "/") result = num1 / num2;

			s.push(result);
		} else {
			s.push(stoi(x));
		}
	}

	return s.top();
}
```


* `stoi` function turns string to int
* stack `.top()` returns the value and pop doesn't
* Remember the order of num1 and num2 are reversed because it is in a stack