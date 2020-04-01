# Introduction

## Reasons for testing

Why would it be a good idea to write automated tests? There are many reasons; here are some of our reasons:

* To find bugs.
* To make sure things won’t break between new code commits.
* To keep tests as living documentations.

## Types of testing

* **Unit tests** that test one isolated unit/ piece of code \(e.g. a function\)

Unit tests are the easiest tests to write because you have some input and can expect some result. There are no dependencies, no complex interactions.

![Unit tests](../.gitbook/assets/image%20%284%29.png)

* **Integration tests** which test the combination of features \(e.g. a function calling another function\)

Integration tests are a bit more complex than unit tests because you now have to deal with some dependencies \(e.g. another function that gets called\).

![Interration tests](../.gitbook/assets/image%20%281%29.png)

* **End-to-End \(e2e\) or UI tests** which test a full interaction path in your app \(e.g. the signup process\)



These kind of tests have a different level of complexity to write them and a different frequency.

![](../.gitbook/assets/image%20%285%29.png)



### 

