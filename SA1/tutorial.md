Add a Wait Page
============================


In this activity, you will learn to add a wait page while the payment is processed.


<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10770111/SA1.gif" width = "480" height = "320">


Follow the given steps to complete this activity:


1. Initiate an HTTP Request to the Server


* Open the `wait.html` file on the Volt Mills.


* Define the function to interact with the payment gateway by creating a new request instance of `XMLHTTPrequest`.
~~~sh
var xhr = new XMLHttpRequest();
xhr.open('GET', 'http://127.0.0.1:4000/checkPaymentStatus', true);
~~~




2. Check if the Server has Processed the Request
* Create a function that is called when there is a change in the `readyState`.
~~~sh
xhr.onreadystatechange = function() {};
~~~
* Log a success message on the console if the readystate is “DONE” and if the server has successfully processed the request or else notify the user with an error message.
~~~sh
if (xhr.readyState === 4) && (xhr.status === 200) {
                    console.log("Response is received!")
          }else {
                 console.error('Error checking payment status:', xhr.status);
                }
        };
~~~
* Check the payment status every 5 seconds by calling the `checkPaymentStatus` function.
~~~sh
setInterval(checkPaymentStatus, 5000);
~~~       


3. Load the Wait Page


*  Open the `cart.js` file.
*  Load the wait page if the user has placed an order in the `placeOrder` function.
~~~javascript
location.replace("wait.html");
~~~


* Save and run the code to check the output.