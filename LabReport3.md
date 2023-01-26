# Lab Report 2 - Servers and Bugs
## Part 1 - StringServer 
The StringServer should use the path and query in the url to print and concatenate strings from incoming requests. <br>
For example inputing the url http://localhost:4000/add-message?s=HelloWorld would print: <br>
![Image](HelloWorld.png)

* **Which methods in your code are called?** <br>
  Processing the url request calls the handleRequest method in my code <br>
  ![Image](HandleClass.png) <br>
* **What are the relevant arguments to those methods, and the values of any relevant fields of the class?** <br>
  The only argument in handleRequest is the url. Using the url, the method then uses the url to create values that are used in the code. The relevant         values in this class include:
    * ArrayList messages - An ArrayList that keeps track of the strings inputed
    * url.getPath() - The path of the url
    * String[] parameters - The query of the url split by = 
    * messages.size() - The amount of strings in messages
    * output - The output returned to the server
* **How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why** <br>
  All the relevant values get changed from this specific request:
    * ArrayList messages - Changes from an empty list to having the string HelloWorld in it
    * url.getPath() - Since this is the first string added, the path changes from just / to /add-message
    * String[] parameters - parameters gets initalized to the new query so it becomes {s, HelloWorld}
    * messages.size() - The size of the list gets increased from 0 to 1
    * output - The output changes by going from nothing to HelloWorld

Now we can add a second message to display. Inputing http://localhost:4000/add-message?s=Goodbye would print: <br>
![Image](Goodbye.png)

* **Which methods in your code are called?** <br>
  Processing the url request calls the handleRequest method in my code <br>
  
* **What are the relevant arguments to those methods, and the values of any relevant fields of the class?** <br>
  The only argument in handleRequest is the url. Using the url, the method then uses the url to create values that are used in the code. The relevant         values in this class include:
    * **ArrayList messages** - An ArrayList that keeps track of the strings inputed
    * **url.getPath()** - The path of the url
    * **String[] parameters** - The query of the url split by = 
    * **messages.size()** - The amount of strings in messages
    * **output** - The output returned to the server
* **How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why** <br>
  All the relevant values get changed from this specific request except url.getPath()
    * **ArrayList messages** - The ArrayList adds the string Goodbye to the list so it now has HelloWorld and Goodbye
    * **url.getPath()** - The path of the url is the same as the last request so it still is /add-message
    * **String[] paramters** - parameters gets initalized in every request so it becomes {s, Goodbye}
    * **messages.size()** - The size of the list gets increased from 1 to 2
    * **output** - The output changes by going from just HelloWorld to HelloWorld + \n + Goodbye which prints HelloWorld and then prints Goodbye on a new         line
## Part 2 - Bugs
   Bug in reversed method in ArrayExamples class <br>
```
# Failure-Inducing Input 
int[] input2 = {1,2,3,4};
assertArrayEquals(new int[]{4,3,2,1}, ArrayExamples.reversed(input2));
```
```
# Non Failure-Inducing Input
int[] input1 = { };
assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
```
Symptom (Output of running the tests) <br>
![Image](Junit.png)

Before Fix: <br>

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  } 
```

After Fix: <br>

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
Explaination: <br>
The bug was that the array that was getting returned was getting set to the newArray that was just initialized. Since newArray is an int array, it would have default values of 0. This is why the tester was expecting 4 but got 0 since the array that was returned was all 0s. To fix this bug I switched arr and newArray in the line right after the for loop so the newArray is the one that is getting set to the reverse of arr. I then made sure to return newArray not arr since newArray is the one that was set to the reverse of arr.

## Part 3 - What Did I Learn?

The most interesting thing that I learned was how to build and run a server. This was totally new to me since I all I knew about computer science was running programs in java. I never knew you could run a whole server from a program. It was interesting seeing how programs can use the url of a server to manipulate what is being returned to the server. Learning how to build and run a server also helped clarify my understanding of how paths and querys work. Running the server on a remote computer also taught me how to use git clone and other git commands to clone a repository to run the server on a remote computer.
 
