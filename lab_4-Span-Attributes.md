# Lab 4: Adding span attributes

In this lab you are going to enhance the ability to identify where Hipster Shop customers are located to better increase revenue. You will do this by adding more context into the trace details with some custom instrumentation.

## A request from marketing
The marketing team and social media PR team are working together on the launch of a new Stetson hat collection for Hipster Shop. They have tapped your team to best identify where ad dollars should be spent across the Unites States. The teams would like to know where orders are being shipped to so they can begin targetting specific states with social media ads. 

## Your plan of action
In an moment of hopeful optimism, you query the data coming into Hipster Shop using the query below but get nothing. Argh!   

*Confirm your environment is functioning the same way  as the screenshot below by attempting to run the same query. Run a similar query for grouping data by city*

![Cursor_and_shippingservice___shippingservice___New_Relic_One.png](images/Cursor_and_shippingservice___shippingservice___New_Relic_One.png)

Next, you look up and down the many functions in the distributed trace you looked at earlier in the lab. You are not able to see an attribute for State, City, or anything simlar to help find the location of shipping orders. What do you do? Order another $7 cappuccino? No! You decide roll up your gingham sleeves a little more to try and figure this out.   

*Confirm your environment is functioning the same way as the lab intends by reviewing a distributed trace and looking at the attributes it provides.*

## Fixing this issue
Realizing that you can't locate or query by the attribute "state" or "city" you know that your next step is to input some custom instrumentation code into the `shippingservice/main.go` file or you risk the chance of hipster's heads across the country not being accompanied by a Stetson hat :scream: 

At this point, your instrumentation provider (OpenTelemetry) is lacking the attribute(s) needed to collect the data you want. You will need to discover a way to import and add those attribute(s) to a span.


**!Note From Tom! ^^ I'm trying to find a way for someone to figure out how to do this on their own but it seems too difficult. I worry people won't know where to begin. Perhaps there is a resource we can provide to help in this process? How can someone figure out for themself to add the childspan and parent span code provided handed to them in the FOK lab?**

## Moving forward in the workshop
Once you have confirmed your ability to track city and state on shipped orders be sure to document your process. When that is done, you are ready to move onto the next lab in this workshop [Lab 5: Passing the torch](lab_5-passing-the-torch.md)