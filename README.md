# EDAServerless
A slice of the AWS ALS code I wrote for the Serverlesspresso hands-on lab I completed during AWS and GOTO's EDA day in Nashville 2023.

During the GOTO EDA day I participated in a hand-on lab demonstrating the capabilities of AWS Serverless solutions, Step Functions, EventBridge, and Dynamo DB to create an application that can accept coffee orders seamlessly through a QR code that allows patrons to order on their mobile phones. The application can accept a selection of coffee orders delivers them to a barista web page where barista's can manage, accept, and complete orders. It is then updated on a main order screen that lists orders, their order number, and if they are being prepared or if they are complete.

The application accepts the coffee order, generates a userID, orderID, and token to pass through the order manager and order processor step functions to manage the order while it is in progress, time out customers if they take too long to order, and react in case a barista takes too long to order.

The code provided handles accepting orders and determining if the shop is open, whether or not it has the capacity to accept another order, await acceptance and completion of the order, and time out the order if it takes too long.
