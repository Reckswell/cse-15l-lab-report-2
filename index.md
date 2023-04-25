# Lab 2 Report
## Part 1

### Code for StringServer
![image](https://user-images.githubusercontent.com/73510375/234178170-d5fa4779-0cb2-4482-a9c1-2f5979e0bb13.png)

### First time using /add-message
![image](https://user-images.githubusercontent.com/73510375/234178145-94334cf2-d021-43a2-b475-f46de1e987b4.png)

Methods Called: `public String handleRequest(URI url)`

Arguments:
* url = `"http://localhost:4444/add-message?s=Test"`
* parameters = `{"s", "Test"}` (taken from splitting the query after `http://localhost:4444/add-message`)
* String out = `Test \n` 

Changes in Values:
* `out = "" + Test \n`

### Second time using /add-message
![image](https://user-images.githubusercontent.com/73510375/234179128-ffe80f4d-d797-4a2d-b1b2-12e533dc5b17.png)

Methods Called: `public String handleRequest(URI url)`

Arguments:
* url = `"http://localhost:4444/add-message?s=Maybe%20this%20isn%27t%20a%20test"`
* parameters = `{"s", "Maybe this isn't a test"}` (taken from splitting the query after `http://localhost:4444/add-message`)
* String out = `"Test \n Maybe this isn't a test \n"` 
