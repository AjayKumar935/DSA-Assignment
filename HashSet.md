

# Hashset

## 1. Write a Java program to check if a given string has all unique characters using a HashSet.

### Code 
``` java

import java.util.HashSet;

public class UniqueCharacters {

	public static void main(String[] args) {
		
		
		String str="abc";
		
		HashSet<Character> set=new HashSet<Character>();
		
		for(int i=0;i<str.length();i++) {
			
			
				set.add(str.charAt(i));
			
			
		}
		
		if(set.size()!=str.length()) {
			System.out.println("The string contains the duplicate characters");
		}
		else {
			System.out.println("The string doesnot conatins any duplicate characters");
		}

	}

}

```


###  Output
``` Java
The string doesnot conatins any duplicate characters
```

## 2. Write a program to find common elements between two ArrayLists using a HashSet.

### Code

``` java
import java.util.ArrayList;
import java.util.HashSet;

public class CommonElements {

	public static void main(String[] args) {
		
		ArrayList<Integer>arr1=new ArrayList<Integer>();
		ArrayList<Integer>arr2=new ArrayList<Integer>();
		
		HashSet<Integer>set=new HashSet<Integer>();
		
		arr1.add(10);
		arr1.add(15);
		arr1.add(20);
		arr1.add(25);
		
		arr2.add(15);
		arr2.add(20);
		arr2.add(30);
		
		for(int i=0;i<arr1.size();i++) {
			
			if(arr2.contains(arr1.get(i))) {
				set.add(arr1.get(i));
			}
			
		}
		
		System.out.println(set);

	}

}

```


###  Output
``` Java
[20, 15]
```


## 3. Write a program to count the number of unique vowels in a given string using a HashSet.

### Code


``` java

import java.util.HashSet;

public class UniqueVowels {

	public static void main(String[] args) {
		
		
		String str="acjouoyrn";
		HashSet<Character> set=new HashSet<Character>();
		
		for(int i=0;i<str.length();i++) {
			
			if(str.charAt(i)=='a' || str.charAt(i)=='e' || str.charAt(i)=='i' || str.charAt(i)=='o' || str.charAt(i)=='u' ) {
				
				set.add(str.charAt(i));
			}
		}
		
		System.out.println(set);

	}

}


```



###  Output
``` Java
[a, u, o]

```
