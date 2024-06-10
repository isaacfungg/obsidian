***
```cpp
# 12345 - False
# 12321 - True

# 12345
# a = 0 
# 12345 % 10 = 5    a = a * 10   a = a + (12345 % 10) = 5 
# 1234 % 10 = 4.    a = a * 10.  a = a + (1234 % 10) = 54
# 123 % 10 = 3      a = a * 10.  a = a + (123 % 10) = 543
# 12 % 10 = 2.      a = a * 10.  a = a + (12 % 10) = 5432
# 1 % 10 = 1        a = a * 10.  a = a + (1 % 10) = 54321 

bool isPalindrome(int num) {
	int reversedNum = 0;
	int temp = num;

	if (num < 0) {
		return false;
	}
	
	while (num > 0) {
		reversedNum *= 10;
		reversedNum += temp % 10;
		temp /= 10;
	}

	return (num == reversedNum);
}
```