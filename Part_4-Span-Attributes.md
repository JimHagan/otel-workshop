# Part 4: Adding Span Attributes

In this exercise you are going to enhance the ability to identify where Hipster Shop customers are located to better increase revenue. You will do this by adding more context into the trace details with some custom instrumentation.

## A request from marketing
The marketing team and social media PR team are working together on the launch of a new Stetson hat collection for Hipster Shop. The have tapped your team to best identify where ad dollars should be spent across the Unites States. The teams would like to know where orders are being shipped to so they can begin targetting specific states with social media ads. 

## Your plan of action
You query the data coming into Hipster Shop using the query below but get nothing. Argh! 
![Cursor_and_shippingservice___shippingservice___New_Relic_One.png](images/Cursor_and_shippingservice___shippingservice___New_Relic_One.png)

Realizing that you can't query by the attribute "state" you know that your next step is to input some custom instrumentation code into the `shippingservice/main.go` file or you risk the chance of hipster's heads across the country not being accompanied by a Stetson hat