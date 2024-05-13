```cpp
vector<int> dailyTemperatures(vector<int>& temperatures) {
	vector<int> result(temperatures.size());
	stack<int> stack;
	for (int i = 0; i < temperatures.size(); i++) {
		while (!stack.empty() && temp[i] > temp[stack.top()]) {
			result[stack.top()] = i - stack.top();
			stack.pop();
		}
		stack.push(i);
	}

	return result;
}
```


how do u manage to work in so many fields?
I started emailing some profs at my uni for cs research but i want to expand my knowledge to different fields but idk how much i would be able to contribute for other fields
