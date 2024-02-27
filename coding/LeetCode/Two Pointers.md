***

#### Valid Palindrome
* A phrase is a palindrome if, after converting all upper case letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward

```Java
public boolean isPalindrome(String s) {
	if (s.isEmpty()) {
		return true;
	}

	int start = 0;
	int lasst = s.length() - 1;

	while (start <= last) {
		char currFirst = s.charAt(start);
		char currLast = s.charAt(last);

		if (!Character.isLetterOrDigit(currFirst)) {
			start++;
		} else if (!Character.isLetterOrDigit(currLast)) {
			last--;
		} else {
			if (Character.toLowerCase(currFirst) != Character.toLowerCase(currLast)) {
				return false;
			}
			start++;
			last--;
		}
	}

	return true;	
}
```


#### Two Sum II - Input Array Is Sorted
* Given a 1-indexed array of integers numbers that is already sorted in non-decreasing order, find two numbers such that they add up to a specific target number. 
```Java
public int[] twoSum(int[] nums, int target) {
	int l = 0;
	int r = nums.length - 1;

	while (nums[l] + nums[r] != target) {
		if (nums[l] + nums[r] < target) {
			l++;
		} else {
			r++;
		}
	}

	return new int[]{l+1, r+1}
}
```