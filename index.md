# Lab 2 Report
## Part 1

### Code for StringServer
![image](https://user-images.githubusercontent.com/73510375/234178170-d5fa4779-0cb2-4482-a9c1-2f5979e0bb13.png)

### First time using /add-message
![image](https://user-images.githubusercontent.com/73510375/234178145-94334cf2-d021-43a2-b475-f46de1e987b4.png)

Methods Called: `public String handleRequest(URI url)`

Arguments:
* URI url = `"http://localhost:4444/add-message?s=Test"`
* String[] parameters = `{"s", "Test"}` (taken from splitting the query after `http://localhost:4444/add-message`)
* String out = `Test \n` 

Changes in Values:
* `out = "" + Test \n`

### Second time using /add-message
![image](https://user-images.githubusercontent.com/73510375/234179128-ffe80f4d-d797-4a2d-b1b2-12e533dc5b17.png)

Methods Called: `public String handleRequest(URI url)`

Arguments:
* URI url = `"http://localhost:4444/add-message?s=Maybe%20this%20isn%27t%20a%20test"`
* String[] parameters = `{"s", "Maybe this isn't a test"}` (taken from splitting the query after `http://localhost:4444/add-message`)
* String out = `"Test \n Maybe this isn't a test \n"`

Changes in Values:
* `out = "Test \n" + "Maybe this isn't a test \n"`

## Part 2
### Method: `static int[] reversed(int[] arr)`

### Failure-inducing input:
![image](https://user-images.githubusercontent.com/73510375/234180547-d87ab69f-41ac-4864-b200-7113f5a416ae.png)

### Non-Failure-inducing input:
![image](https://user-images.githubusercontent.com/73510375/234180570-99a3b095-7e0d-4950-bb36-76e4b06b0b7e.png)

### Symptoms:
![image](https://user-images.githubusercontent.com/73510375/234180609-016be374-deef-4337-a45e-bd1cbd511a5c.png)

### Bug Fix:
Before: 
![image](https://user-images.githubusercontent.com/73510375/234180288-d806f832-7015-4e33-9b08-1d0ef9256610.png)

After:
![image](https://user-images.githubusercontent.com/73510375/234181079-aee3fc25-d252-4318-9dd8-a874c8d1d4bf.png)

Before the fix, the code would just 

