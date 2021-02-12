#Exercise 11.4
##Create an AWS Step functions State Machine 1
In this exercise, you will create an AWS Step Functions state machine. The state machine will extract price and quantity from the input and inject the billing amount into the output.
This state machine will calculate how much to bill a customer based on the price and quantity of an item they purchased.
1.	Sign in to the AWS Management Console and open the Step Functions console at
*https://console.aws.amazon.com/step-functions/*.
2.	Select **Get Started**.
3.	On the **Define state machine** page, select **Author from scratch**.
4.	In **Name type**, enter *order-machine*.
5.	Enter the code for the state machine definition.
This is the code that you downloaded at the beginning of the exercises.
```
{
  "StartAt": "CreateOrder",
  "States": {
    "CreateOrder": {
      "Type": "Pass",
      "Result": {
        "Order" : {
          "Customer" : "Alice",
          "Product" : "Coffee",
          "Billing" : { "Price": 10.0, "Quantity": 4.0 }
        }
    },
    "Next": "CalculateAmount"
},
"CalculateAmount": {
  "Type": "Pass",
  "Result": 40.0,
  "ResultPath": "$.Order.Billing.Amount",
  "OutputPath": "$.Order.Billing",
  "End": true
   }
 }
}
```
6.	On the State **machine definition** page, select **Reload**.
This updates the visual representation of the state machine. The state machine con-  sists of two states: *CreateOrder* and *CalculateAmount*. They are both Pass types and pass hardcoded values.
This is useful for build  the  outline  of  your  final  state machine.  You  can  also  use  this to debug *ResultPath* and *OutputPath*. *ResultPath* determines where in the input to inject the result. *OutputPath* determines what data passes to the next state.
7.	Select **Create state machine**.
8.	Select  **Start execution**.
9.	In **Input type**, enter {}.
10.	Select  **Start execution**.
11.	Expand **Output**, and it should look like the following:
```
    {
      "Price": 10,
      "Quantity": 4,
      "Amount": 40
    }
```
In *CalculateAmount, "ResultPath"*: *"$.Order.Billing.Amount"* injected Amount under Billing under Order. Then in the same element, *"OutputPath": "$.Order. Billing"* threw away the rest of the input and passed only the contents of the Billing element forward. This is why the output contains only *Price, Quantity,* and *Amount*.
12.	(Optional) Experiment with different values of *ResultPath* to understand how it affects where the result of a state inserts into the input.
13.	(Optional) Experiment with different values of *OutputPath* to understand how it affects what part of the data passes to the next state.
