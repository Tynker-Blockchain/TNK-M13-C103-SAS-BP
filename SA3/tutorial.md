Confirm the Payment
===================




In this activity, you will learn to confirm the payment.




<img src= "https://s3.amazonaws.com/media-p.slid.es/uploads/1525749/images/10770118/SA3.gif" width = "480" height = "320">


Follow the given steps to complete this activity:


1. Create a Payment Status


* Open the file `app.py`.


* Create a variable to keep track of the payments and set it to None.
~~~python
paymentStatus = None
~~~


2. Set the Payment Status to True After Making the Transaction


* Access the global variables `receiverAddress, tnxAmount, paymentStatus` in the `makeTransaction` function definition.
~~~python
global myWallet, account, receiverAddress, tnxAmount, paymentStatus
~~~
* Reset the receiver address, transaction amount to `None`, and the payment status to `True` after the transaction is made.
~~~python
if(receiverAddress):
        receiverAddress = None
        tnxAmount = None
        paymentStatus = True
~~~


3. Send the Payment Confirmation
* Reset the payment status to `None` after the payment status response is sent to the request.
* Access the global variable `paymentStatus` in the `checkPaymentStatus` function definition.
~~~python
def checkPaymentStatus():
    global paymentStatus
~~~
* Send a `True` response if the payment status is `True` and reset the payment status to `None`.
~~~python
def checkPaymentStatus():
    global paymentStatus
 	if paymentStatus == True:
        paymentStatus = None
        return jsonify(True)
~~~
* Send the payment status if the payment status is not `True`.
~~~python
def checkPaymentStatus():
    global paymentStatus
 	if paymentStatus == True:
        paymentStatus = None
        return jsonify(True)
    return jsonify(paymentStatus)
~~~
* Save and run the code to check the output.

* Make sure to open the voltmills website in view mode by replacing "project" with "view" in the url and add / at the end of url. eg: https://tynker.me/code/view/65094444899d76597e769782/
