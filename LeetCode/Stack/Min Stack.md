```cpp
class MinStack{
public: 

	vector<pair<int, int>> s;
	MinStack() {
	
	}

	void push(int val) {
		if (s.empty()) {
			s.push_back({val, val});
		} else {
			s.push_back(val, min(val, s.back().second);
		}
	}

	void pop() {
		s.pop_back();
	}

	int top() {
		return s.back().first;
	}

	int getMin() {
		return s.back().second;
	}
}
```

* pop_back()
* Have a pair with the second value being the min value of all the values of itself and before