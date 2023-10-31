Send the Payment ID Status
==============




In this activity, you will learn to send the payment status for the specific order.


<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10770121/SA3.gif" width = "480" height = "320">


Follow the given steps to complete this activity:


1. Define the method to send the payment ID status to the Volt Mills web page.
Note: The code to display the status of the specific payment ID is already done for you.
* Open the file `app.py`.


* Access the global variable `PaymentID_Status` from the `checkPaymentStatus()` function.
~~~python
global PaymentID_Status
~~~
* Update the status of the response if the ID is present in PaymentID_Status and its status is success.
~~~python
if "ID" in PaymentID_Status and PaymentID_Status["Status"] == "success":
        response = {
            "status": "success",
            "paymentID": PaymentID_Status["ID"]
        }
else:
        response = {
            "status": "processing"
        }
~~~
* Send the response to the Volt Mills web page. 
~~~python
return jsonify(response)
~~~
* Save and run the code to check the output.