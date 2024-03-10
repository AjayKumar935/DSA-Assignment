# ArrayList

## 1. Write a program to merge two sorted ArrayLists into a single sorted ArrayList without using any built-in sorting functions.

Code <br>

``` java

import java.util.ArrayList;

public class MergeTwoArrays {
	 public static ArrayList<Integer> merge(ArrayList<Integer> list1, ArrayList<Integer> list2) {
		 
		 ArrayList<Integer>res=new ArrayList<Integer>();
		 
		 int i=0,j=0;
		 
		 while(i<list1.size() && j< list2.size()) {
			 
			 if( list1.get(i) <list2.get(j)) {
				 res.add(list1.get(i));
				 i++;
			 }
			 else {
				 res.add(list2.get(j));
				 j++;
			 }
		 }
		 
		 
		 while(i<list1.size() ){
			 res.add(list1.get(i));
			 i++;
		 }
		 
		 while(j<list2.size()) {
			 res.add(list2.get(j));
			 j++;
		 }
		 
		 
		 return res;
	
}
	

	public static void main(String[] args) {
		
		ArrayList<Integer>list1=new ArrayList<Integer>();
		ArrayList<Integer>list2=new ArrayList<Integer>();
		
		list1.add(1);
		list1.add(1);
		list1.add(9);
		list1.add(10);
		list1.add(20);
		
		list2.add(1);
		list2.add(5);
		list2.add(8);
		
		ArrayList<Integer>result=merge(list1,list2);
		System.out.println(result);

	}
}



```


### Output
``` Java
[1, 1, 1, 5, 8, 9, 10, 20]
```


## 2. Implement a sorting function for an ArrayList of strings that sorts them based on the length of the strings in ascending order.
 ### code
``` java

import java.util.ArrayList;

public class SortStringsOnSize {
	 static void sortByLength(ArrayList<String> strings) {
			
		 int n=strings.size();
		 
		 for(int i=0;i<n-1;i++) {
			 
			 for(int j=0;j<n-i-1;j++) {
				 
				 if(strings.get(j).length() > strings.get((j+1)).length()) {
					 String temp=strings.get(j);
					 strings.set(j, strings.get(j+1));
					 strings.set(j+1, temp);
				 }
			 }
		 }
			
		}

	public static void main(String[] args) {
		
		ArrayList<String>strings=new ArrayList<String>();
		strings.add("abc");
		strings.add("ab");
		strings.add("aaaaa");
		strings.add("a");
		
		sortByLength(strings);
		
		System.out.println(strings);

	}

}

```

### Output
``` Java
[a, ab, abc, aaaaa]

```

## 3. Check if an ArrayList of strings is a palindrome.
``` java
import java.util.ArrayList;

public class CheckPalindrome {
	
	 static boolean isPalindrome(ArrayList<String> strings) {
		 
		 int left=0;
		 int right=strings.size()-1;
		 
		 while(left<right) {
			 
			 if(!strings.get(left).equals(strings.get(right))) {
				 return false;
			 }
			 left++;
			 right--;
		 }
		return true;
	}

	public static void main(String[] args) {
		
		ArrayList<String> strings=new ArrayList<String>();
		strings.add("madam");
		strings.add("racecar");
		strings.add("madam");
		
		boolean result=isPalindrome(strings);
		
		if(result) {
			System.out.println("The given arrayList is palindrome");
		}
		
		else {
			System.out.println("The given arrayList is not Palindrome");
		}
	}
}
```

### Output
``` Java
The given arrayList is palindrome


```
