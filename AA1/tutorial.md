Create Payment ID
=================




In this activity, you will learn to add a unique ID for each payment request done and update its status.




<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10770121/SA3.gif" width = "480" height = "320">


Follow the given steps to complete this activity:
	
1. Store the unique payment IDs and its status.


* Open the file `app.py`.


* Initialize a variable to a dictionary to store the payment IDs and its status.
~~~python
PaymentID_Status = {}
~~~
* Access the global variable `PaymentID_Status` in the `payment()` function.
~~~python
global receiverAddress, tnxAmount, requestUrl, paymentStatus, paymentID, PaymentID_Status
~~~
Note: The code to calculate the payment ID is already done for you. The calculations are done in `wait.html` and sent to the payment gateway.


* Extract the payment ID from the URL and update the status to processing.
~~~python
paymentID = request.args.get("paymentID")
paymentStatus = "processing"
~~~


* Add the payment ID and its status to the `PaymentID_Status` dictionary. Print the list of pending payments.
~~~python
PaymentID_Status = {
        "ID": paymentID,
        "Status": paymentStatus
    }
    print("List",PaymentID_Status)
~~~
* Access the global variable `PaymentID_Status` from the `makeTransaction()` function.
~~~python
 global myWallet, account, receiverAddress, tnxAmount, paymentStatus, PaymentID_Status
~~~
* Update and print the `PaymentID_Status` after the transaction is successful.
~~~python
 if "ID" in PaymentID_Status:
            PaymentID_Status["Status"] = "success"
 print(PaymentID_Status)
~~~
* Save and run the code to check the output.