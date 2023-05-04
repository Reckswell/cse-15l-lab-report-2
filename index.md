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
<br> ![image](https://user-images.githubusercontent.com/73510375/234180288-d806f832-7015-4e33-9b08-1d0ef9256610.png)

After:
<br> ![image](https://user-images.githubusercontent.com/73510375/236319989-cc55124d-1fa1-4b74-b3e7-212aa5cacced.png)

Before the fix, the code would iterate everything in `newArray` into `arr`, but since `newArray` is empty, it returns an empty array. 
To fix this, you need to iterate the values of `arr` backwards into `newArray` with the index counting backwards instead of forwards (hence the `arr.length - 1 - i`, with i accounting for the index and -1 accounting for the index difference to prevent out of bounds).

## Part 3
Something which I didn't know about before the lab in week 2 was the idea of how queries were split inside a url. Before the lab, I had an idea of how queries and urls worked, but didn't know the process of how to differentiate between different queries (ex. how does a code know to add a space, since you can't have a space in a url). After the lab, and this lab report, I found out that a query is split based on it's command (or the action to execute), and the parameters (or a given string). I also learned that spaces are separated with a percentage symbol in the url bar.

