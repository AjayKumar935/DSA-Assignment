# HashMap of Array
## 1. Use a HashMap to manage employee records, allowing operations like adding, updating, and deleting employee details. -  use more than 2 employee records.
###  code
``` java

import java.util.HashMap;

public class EmployeeRecords {
	
	
	public static StringBuilder arrayToString(String [] arr) {
		
        StringBuilder sb = new StringBuilder();
		
		for (int i = 0; i < arr.length; i++) {
            sb.append(arr[i]);
            if (i < arr.length - 1) {
                sb.append(", ");
            }
        }
		
		
		
		return sb;
	}
	

	public static void main(String[] args) {
		
		HashMap<Integer, String[] >empMap=new HashMap<Integer, String[]>();
		
		empMap.put(1, new String[]{"AjayA","20","Tech Consultant"});
		empMap.put(2, new String[]{"Anil","23","Process Consultant"});
		empMap.put(3, new String[]{"Aman","22","Bank Employee"});
		empMap.put(4, new String[]{"Abhi","20","Data entry"});
		
		
		empMap.forEach((key,value)->{
			System.out.println("The key is "+key +" The value is "+arrayToString(value));
		});
		
		
		empMap.remove(1);
		empMap.forEach((key,value)->{
			System.out.println("The key is "+key +" The value is "+arrayToString(value));
		});
		
		String updateRecord[]=empMap.get(2);
		updateRecord[1]="30";
		updateRecord[2]="Manager";
		
		empMap.forEach((key,value)->{
			System.out.println("The key is "+key +" The value is "+arrayToString(value));
		});
		
		
		
		

		}

	}



```


### output

``` java

The key is 1 The value is AjayA, 20, Tech Consultant
The key is 2 The value is Anil, 23, Process Consultant
The key is 3 The value is Aman, 22, Bank Employee <br>

The key is 4 The value is Abhi, 20, Data entry
The key is 2 The value is Anil, 23, Process Consultant
The key is 3 The value is Aman, 22, Bank Employee <br>

The key is 4 The value is Abhi, 20, Data entry
The key is 2 The value is Anil, 30, Manager <br>

The key is 3 The value is Aman, 22, Bank Employee
The key is 4 The value is Abhi, 20, Data entry

```


## 2. Create a library catalog system using a HashMap to store book details (title, author, and availability status). - use more than 4 book details.

### code


``` java
import java.util.HashMap;

public class bookStore {
	
	
		static void display(HashMap<String, String[]> map) {
		    map.forEach((key, value) -> {
		        System.out.println("The Book name is " + key); 
		        for (int i = 0; i < value.length; i++) {
		            if (i == 0) {
		                System.out.println("The Author is " + value[0]);
		            }
		            if (i == 1) {
		                System.out.println("The availability is " + value[1]); 
		            }
		        }
		        System.out.println();
		    });
		}

	
	
	public static void main(String[] args) {
		
		
		HashMap<String,  String[]>map=new HashMap<String, String[]>();
		
		map.put("James Clear", new String[] {"The Atomic Habits", "Available"} );
		
		map.put("Robert Kiyosaki" ,new String[] {"Rich Dad Poor Dad","Unavilable"});
		
		map.put("The Psychology of Money", new String[] {"Morgan Housel","Available"});
		
		display(map);
		
		
		//After the updation.
		
		String updateRecord[]=map.get("Robert Kiyosaki");
		
		updateRecord[1]="Available";
		
		display(map);
		
		
		
		
		//After the Deletion
		map.remove("James Clear");
		
		display(map);
		
		

	}

}

```

### output

``` java
The Book name is James Clear
The Author is The Atomic Habits
The availability is Available

The Book name is The Psychology of Money
The Author is Morgan Housel
The availability is Available

The Book name is Robert Kiyosaki
The Author is Rich Dad Poor Dad
The availability is Unavilable

The Book name is James Clear
The Author is The Atomic Habits
The availability is Available

The Book name is The Psychology of Money
The Author is Morgan Housel
The availability is Available

The Book name is Robert Kiyosaki
The Author is Rich Dad Poor Dad
The availability is Available

The Book name is The Psychology of Money
The Author is Morgan Housel
The availability is Available

The Book name is Robert Kiyosaki
The Author is Rich Dad Poor Dad
The availability is Available

```


## 3. Problem: Create a hashmap that stores the names of cars as keys and their corresponding prices as an array of values. Then, write a function that takes in a car name and returns the average price of that car across all available models.
## Sample Input:{  "Honda": [20000, 25000, 28000],
##  "Toyota": [22000, 24000, 27000], 
## "Ford": [19000, 23000, 26000]}

### code

``` java
import java.util.HashMap;

public class carPrices {
	
	public static int findAverage(Integer[] cars) {
		int sum=0;
		
		
		for(int i=0;i<cars.length;i++) {
			sum+=cars[i];
		}
		
		
		
		return sum/cars.length;
	}

	public static void main(String[] args) {
		
		
		HashMap<String, Integer[]>map = new HashMap<String, Integer[]>();
		
		map.put("Honda", new Integer[] {20000, 25000, 28000});
		map.put("Toyota", new Integer[] {22000, 24000, 27000});
		map.put("Ford", new Integer[] {19000, 23000, 26000});
		
		
		Integer[] cars=map.get("Honda");
		
		int average=findAverage(cars);
		
		System.out.println("The average price os the Honda is "+average);

	}

}

```


### output


``` java
The average price os the Honda is 24333

```
