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
* **How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
   
  
