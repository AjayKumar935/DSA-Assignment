# HashMap

## 1. Write a Java program that takes a string as input and returns a HashMap containing the frequency of each character in the string. The keys of the map should be characters, and the values should be the number of times each character appears in the string.

### code

``` java

import java.util.HashMap;

public class FrequencyOfCharacters {

	public static void main(String[] args) {
		
		HashMap<Character, Integer> map=new HashMap<Character, Integer>();
		
		String str="Hello world";
		
		
		for(int i=0;i<str.length();i++) {
			
			if(map.containsKey(str.charAt(i))) {
				
				map.put(str.charAt(i), map.get(str.charAt(i))+1 );
			}
			else {
				map.put(str.charAt(i), 1);
			}
		}
		
		System.out.println(map);

	}

}

```

### output

``` java
{ =1, r=1, d=1, e=1, w=1, H=1, l=3, o=2}

```

## 2. Write a Java function that takes two HashMaps as input and returns a new HashMap containing only the key-value pairs that are common to both input maps. If a key is present in both maps but with different values, consider only the values from the first map


### code

``` java

import java.util.HashMap;

public class MergeHashMaps {
	
	public static HashMap<String, Integer> mergeHashMaps(HashMap<String, Integer> map1,HashMap<String, Integer> map2) {
		
		HashMap<String, Integer>res=new HashMap<String, Integer>();
		
		map1.forEach((key,value)->{
			
			if(map2.containsKey(key)) {
				
				res.put(key, value);
			}
		});
		
		
		return res;

	}

	public static void main(String[] args) {
		
		HashMap<String, Integer>map1=new HashMap<String, Integer>();
		HashMap<String, Integer>map2=new HashMap<String, Integer>();
		
		map1.put("Ajay", 1);
		map1.put("Anil", 2);
		map1.put("Aman", 3);
		
		map2.put("Ajay", 1);
		map2.put("Amar", 1);
		map2.put("Akhil", 2);
		map2.put("Aman", 6);
		
		HashMap<String, Integer>res=mergeHashMaps(map1,map2);
		System.out.println(res);
		
	}
}

```


### output
``` java
{Aman=3, Ajay=1}
```

##  3. Given an array of integers, find the frequency of each integer using a HashMap.
## Input: [1, 2, 3, 1, 4, 2, 5, 6, 7, 1, 8, 9, 9] 
## Output: {1=3, 2=2, 3=1, 4=1, 5=1, 6=1, 7=1, 8=1, 9=2} 


### code

``` java
import java.util.ArrayList;
import java.util.HashMap;

public class FrequencyOfIntegers {

	public static void main(String[] args) {
		
		ArrayList<Integer>arr=new ArrayList<Integer>();
		
		HashMap<Integer, Integer>map=new HashMap<Integer, Integer>();
		
		//[1, 2, 3, 1, 4, 2, 5, 6, 7, 1, 8, 9, 9]
		
		arr.add(1);
		arr.add(2);
		arr.add(3);
		arr.add(1);
		arr.add(4);
		arr.add(2);
		arr.add(5);
		arr.add(6);
		arr.add(7);
		arr.add(1);
		arr.add(8);
		arr.add(9);
		arr.add(9);
		
		for(int i=0;i<arr.size();i++) {
			
			if(map.containsKey(arr.get(i))) {
				
				map.put(arr.get(i), map.get(arr.get(i)) +1 );
			}
			
			else {
				map.put(arr.get(i), 1);
			}
		}
		
		System.out.println(map);
	}
}


```

### output
``` java
{1=3, 2=2, 3=1, 4=1, 5=1, 6=1, 7=1, 8=1, 9=2}

```
