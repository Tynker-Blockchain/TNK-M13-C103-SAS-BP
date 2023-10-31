Send and Receive Response
===========================


In this activity, you will learn to send a response from the server and receive it on the wait page.


<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10770113/SA2.gif width = "480" height = "320">


Follow the given steps to complete this activity:


1. Create a Route to Send a Response


* Open the file `app.py`.


*  Create a route to send a response to the `checkPaymentStatus` request.
~~~python
@app.route('/checkPaymentStatus')
def checkPaymentStatus():
    return jsonify(True)
~~~
2. Receive the Response
* Open the file `wait.html` on the Volt Mills web page.
* Receive the response to the `checkPaymentStatus` request if the HTML status is 200. Store the response string after converting it to a JavaScript object.
~~~sh
var response = JSON.parse(xhr.responseText);
~~~
* Call the `placeOrder` function if the server response is true.
~~~sh
if(response == true){
    placeOrder()
}
~~~ 
2. Place the Order  
* Place the order by uncommenting the `placeOrder` function definition.
~~~sh
function placeOrder(){
    cart = localStorage.getItem("cart")
    cart = JSON.parse(cart)
    ...
    ...
      location.replace("signup.html");
    }
}
~~~


* Save and run the code to check the output.