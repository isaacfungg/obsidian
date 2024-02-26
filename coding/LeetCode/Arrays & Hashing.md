***
#### Contains Duplicate
* Can use a set to check if there are any duplicates
```Java
HashSet<Integer> seen = new HashSet<>();

for (int num : nums) {
	if (seen.contains(num))
		return true;
	seen.add(num);
}

return false;
```

#### Valid Anagram
**Method 1 (nlogn)** 
* Turn strings to char array
* Sort the array
* Compare the array
**Method 2**: 
* Using a Hash Table
```Java
Map<Character, Integer> count = new HashMap<>();

for (char x : s.toCharArray) {
	count.put(x, count.getOrDefault(x, 0) + 1);
}

for (char x : t.toCharArray()) {
	count.put(x, count.getOrDefault(x, 0) - 1);
}

for (int val : count.values()) {
	if (val != 0) {
		return false;
	}
}

return true;
```

#### Two Sum
**Method 1:**
* Brute force
**Method 2:** 
* Hash Table to track elements in the array
```Java
public int[] twoSum(int[] nums, int target) {
	Map<Integer, Integer> map = new HashMap<>();

	for (int i = 0; i < nums.length; i++) {
		int complement = target - nums[i];
		
		if (map.containsKey(complement)) {
			return new int[]{map.get(complement), i};
		}

		map.put(nums[i], i);
	}

	return new int[]{};
}
```


#### Group Anagrams
* Given an array of strings strs, group the anagrams together. You can return the answer in any order
```Java
public List<List<String>> groupAnagrams(String[] strs) {
	HashMap<String, List<String>> map = new HashMap<>();

	for (String word : str) {
		char[] chars = word.toCharArray();
		Arrays.sort(chars);

		String sortedWord = new String(chars);

		if (!map.containsKey(sortedWord)) {
			map.put(sortedWord, new ArrayList<>());
		}

		map.get(sortedWord).add(word);
	}

	return new ArrayList<>(map.values());
}
```

#### Top K Frequent Elements
* Given an array **nums** and an integer **k**, return the k most frequent elements. 
```Java
public int[] topKFrequent(int[] nums, int k) {
	HashMap<Integer, Integer> map = new HashMap<>();

	for (int i = 0; i < nums.length; i++) {
		map.put(nums[i], map.getOrDefault(nums[i], 0) + 1);
	}

	ArrayList<Integer> list = new ArrayList<>(map.values());
	Collections.sort(list, Collections.reverseOrder());
	ArrayList<Integer> list2 = new ArrayList<>(list.subList(0, k));

	
	
}
```