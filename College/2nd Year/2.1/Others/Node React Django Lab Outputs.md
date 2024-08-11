# **1. Build a responsive web application for shopping cart with registration, login, catalog and cart pages using CSS3 features, flex and grid**

## Output: 
The shopping cart application's basic structure is displayed in index.html, with the 
catalog section containing dummy product data

![[Pasted image 20231210192518.png]]
# **2. Make the above web application responsive using Bootstrap framework**
## Output:
When you open `index.html` in a web browser, you'll see that the web application is now responsive. The Bootstrap framework takes care of making the layout adapt to different screen sizes, providing a more user-friendly experience on various devices.

Remember to test the responsiveness by resizing your browser or using different devices to see how the layout adjusts.

![[Pasted image 20231210193543.png]]

# **3. Use JavaScript for doing client–side validation of the pages implemented in experiment 1 and experiment 2**

## Outputs

### Experiment 1:

![[Pasted image 20231210194904.png]]
### Experiment 2:

![[Pasted image 20231226183645.png]]
# **4. Explore the features of ES6 like arrow functions, callbacks, promises, async/await. Implement an application for reading the weather information from openweathermap.org and display the information in the form of a graph on the web page**

## Outputs
![[WhatsApp Image 2023-12-23 at 11.50.24_fb2e0619.jpg]]
# **5. Develop a Java stand-alone application that connects with the database (Oracle / MySQL) and perform the CRUD operation on the database tables**
## Outputs
```
Record created successfully.

ID Name 	 Salary
1  John Doe      50000

Record updated successfully.

ID Name 	 Salary
1  John Updated  55000

Record deleted successfully.

ID   Name   Salary
```
# **6. Create an XML for the bookstore. Validate the same using both DTD and XSD**
## Outputs
```
Validation with DTD successful.
Validation with XSD successful.

Book 1:
Title: Introduction to XML
Author: John Doe
Price: 29.99

Book 2:
Title: Web Development Basics
Author: Jane Smith
Price: 39.95
```

# **7. Design a controller with servlet that provides the interaction with the application developed in experiment 1 and the database created in experiment 5**

---
---
---

# **8. Maintaining the transactional history of any user is very important. Explore the various session tracking mechanisms (Cookies, HTTP Session)**
## Outputs
1. **Cookies:**
![[Pasted image 20240120205031.png]]

When "Set language to English" is clicked:
![[Pasted image 20240120205045.png]]

When "Go back to the home page" is clicked:
![[Pasted image 20240120205056.png]]

2. **HTTP Session:**
![[Pasted image 20240120205510.png]]

When page is refreshed multiple times:

![[Pasted image 20240120205523.png]]
# **9. Create a custom server using http module and explore the other modules of Node.js like OS, path, event**
## Outputs
1. **Creating a Custom Server with http Module:**
![[Pasted image 20240120205708.png]]
2. **Exploring Node.js Modules:**
*A. OS Module:*
```
OS Platform: win32
OS Architecture: x64
Total Memory (in bytes): 8262680576
Free Memory (in bytes): 748179456
```
*B. path Module:*
```
File Name: file.txt
Directory Name: /path/to/some
File Extension: .txt
```
*C. events Module:*
```
Event triggered with argument: Hello, EventEmitter!
```
# **10. Develop an Express web application that can interact with REST API to perform CRUD operations on student data. (Use Postman)**
## Outputs
1. **Create**: Send a POST request to http://localhost:3000/students with JSON body containing student data. 
![[Pasted image 20240120213106.png]]
2. **Read (All):** Send a GET request to http://localhost:3000/students. 
![[Pasted image 20240120224449.png]]
3. **Read (One):** Send a GET request to http://localhost:3000/students/{student_id}. 
![[Pasted image 20240120213233.png]]
4. **Update**: Send a PATCH request to http://localhost:3000/students/{student_id} with the updated data. 
![[Pasted image 20240120213519.png]]
5. **Delete**: Send a DELETE request to http://localhost:3000/students/{student_id}.
![[Pasted image 20240120213606.png]]
# **11. For the above application, create authorized endpoints using JWT (JSON Web Token)**
## Outputs
1. **Authentication**:
![[Pasted image 20240120214209.png]]
2. **Access Protected Endpoints**:
![[Pasted image 20240120214621.png]]
![[Pasted image 20240120224550.png]]

# **12. Create a React application for the student management system having registration, login, contact, about pages and implement routing to navigate through these pages**
![[Pasted image 20240120223636.png]]
![[Pasted image 20240120223628.png]]
![[Pasted image 20240120223714.png]]
# **13. Create a service in React that fetches the weather information from openweathermap.org and then display the current and historical weather information using graphical representation using chart.js**
![[Pasted image 20240121001145.png]]
# **14. Create a TODO application in React with necessary components and deploy it into GitHub**
![[Pasted image 20240120235741.png]]

```
cd react-todo-app
git init
git add .
git commit -m "todo react app"
git remote add origin https://github.com/your-username/your-repo-name.git
git push -u origin master

```