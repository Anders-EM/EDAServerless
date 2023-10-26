# EDAServerless
A slice of the AWS ALS code I wrote for the Serverlesspresso hands-on lab I completed during AWS and GOTO's EDA day in Nashville 2023.

During the GOTO EDA day I participated in a hand-on lab demonstrating the capabilities of AWS Serverless solutions, Step Functions, EventBridge, and Dynamo DB to create an application that can accept coffee orders seamlessly through a QR code that allows patrons to order on their mobile phones. The application can accept a selection of coffee orders delivers them to a barista web page where barista's can manage, accept, and complete orders. It is then updated on a main order screen that lists orders, their order number, and if they are being prepared or if they are complete.

The application accepts the coffee order, generates a userID, orderID, and token to pass through the order manager and order processor step functions to manage the order while it is in progress, time out customers if they take too long to order, and react in case a barista takes too long to order.

Serverlesspresso Order Processing Workflow:
This AWS Step Functions state machine manages the order processing for the Serverlesspresso application. It automates the workflow from checking the shop's availability to order completion, seamlessly handling various tasks and potential issues like shop capacity and task timeouts.

Key Features
Shop Status Check: Determines if the shop is open and ready to process orders.
Order Capacity Management: Ensures the shop doesn't exceed its capacity to handle orders.
Order Progress Tracking: Manages order states from initiation to fulfillment, using task tokens to track progress and handle timeouts.
Error and Timeout Handling: Gracefully manages scenarios where customers or baristas don't act, ensuring the system remains responsive and accurate.
Event Notifications: Emits detailed events at each stage, allowing for external systems integration or monitoring setups.
