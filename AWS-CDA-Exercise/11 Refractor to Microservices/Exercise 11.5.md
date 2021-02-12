#Exercise 11.5
##Create an AWS Step functions State Machine 2
In this exercise, you will  create an  AWS  Step  Functions  state machine.  The state machine will contain a conditional branch. It will use the Choice state to choose which state to transition to next.
The state machine inspects the input and based on it decides whether the user ordered green tea, ordered black tea, or entered invalid input.
1.	Sign in to the AWS Management Console and open the Step Functions console at:
*https://console.aws.amazon.com/step-functions/*.
2.	Select **Get Started**.
3.	On the **Define state machine** page, select **Author from scratch**.
4.	In **Name type**, enter tea-machine.
5.	Enter the state machine definition.
  This is the code that you downloaded at the beginning of the exercises.
```
    {
      "Comment" :
        "Input should look like {'tea':'green'} with double quotes instead of single.",
        "StartAt": "MakeTea",
        "States" : {
          "MakeTea": {
            "Type": "Choice",
            "Choices": [
              {"Variable":"$.tea","StringEquals":"green","Next":"Green"},
              {"Variable":"$.tea","StringEquals":"black","Next":"Black"}
        ],
          "Default": "Error"
      },
      "Green": { "Type": "Pass", "End": true, "Result": "Green tea" },
      "Black": { "Type": "Pass", "End": true, "Result": "Black tea" },
      "Error": { "Type": "Pass", "End": true, "Result": "Bad input" }
    }
  }
```
6.	On the **State machine definition** page, select **Reload**.
This updates the visual  representation of  the  state machine.  The MakeTea state is a Choice state. Based on the input it receives, it will branch out to Green, Black, or Error.
7.	Select **Create state machine**.
8.	Select **Start execution**.
9.	In **Input type**, enter this value:
```
{ "tea" : "green" }
```
10.	Select **Start execution**.
11.	Select **Expand Output**, and it should look like this:
```
"Green tea"
```
12.	(Optional) Experiment with different inputs to the state machine. For example, try the following inputs:
For **Input type**, enter *black tea*. This input works.
```
{ "tea" : "black" }
```
For **Input type**, enter *orange tea*. This produces an error.
```
{ "tea" : "orange" }
```
13.	Change the state machine so that orange tea also works.
