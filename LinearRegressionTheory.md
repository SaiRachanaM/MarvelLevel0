### 1. Introduction  
Linear Regression is one of the simplest and most widely used techniques in machine learning. It tries to draw a straight line through a set of points in such a way that the line best represents the relationship between the input (called the feature) and the output (the value we want to predict).
![intro png](https://i.imgur.com/eW7mAFA.png)
The straight line has two important parts:  
- **Slope (m)** → tells us how steep the line is.  
- **Intercept (b)** → tells us where the line crosses the y-axis.  
The formula is:  
![the formula](https://i.imgur.com/M9tumpw.png)    
where:    
- x = input,  
- hat{y} = predicted output,  
- m and b are numbers we must “learn.”  
### 2. Predictions (Hypothesis Function)  
When we feed an input value into the equation, the model predicts an output.  
Example:  
If m = 2, b = 1, and x = 3, then  
hat{y} = 2 * 3 + 1 = 7
### 3. Measuring Error (Loss Function)  
Since predictions will not be perfect at the start, we need a way to measure how wrong they are.  
The most common measure is **Mean Squared Error (MSE)**:
![error png](https://i.imgur.com/NgjXfim.jpeg)
![the formula](https://i.imgur.com/10ZAIaM.png)  
- Squared error ensures negatives don’t cancel positives, and big mistakes count more  
### 4. Gradient Descent (Learning the Best Line)  
To make the line fit the data better, we need to adjust \(m\) and \(b\) until the error (MSE) is as small as possible.  
We do this using **Gradient Descent**.  

Think of it like standing on a hill (the error surface) and trying to walk down into the valley (minimum error). Each step you take is in the direction of the steepest downhill slope.
![the graph](https://i.imgur.com/41rJEWl.png)

#### How It Works Step by Step
1. Start with random values of m and b.  
2. Use them to make predictions.  
3. Calculate the error (MSE).  
4. Calculate how the error changes if m or b are adjusted a little → this is the **gradient**.  
5. Update m and b using the formulas:
    ![the formula](https://i.imgur.com/0bs9Lce.png)
   where alpha is the learning rate/step size.

7. Repeat steps 2-5 many times until the error becomes very small i.e. close to zero or till the maximum step count is reached.  
![gif1](https://i.imgur.com/x439HBi.gif)
![gif2](https://i.imgur.com/Zz7K4J3.gif)
### 5. The Math Behind the Gradients  
The gradient is just the slope of the error with respect to each parameter.  
![the formula](https://i.imgur.com/iZPo6jy.png)  
These formulas tell us the “direction” to move in to reduce the error.  
### 6. Normalization (Why It Helps)  
If our input values \(x\) have very large numbers (like house prices in lakhs vs. room sizes in single digits), gradient descent can become very slow or unstable.  
To fix this, we scale the features so they are on a similar range. Two common methods:  
![the formula](https://i.imgur.com/XAoOG0i.png)  
Normalization helps gradient descent converge faster and prevents one feature from dominating the learning.  
