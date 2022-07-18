# Part 4: Adding Span Attributes

In this exercise you are going to enhance the ability to identify where Hipster Shop customers are located to better increase revenue. You will do this by adding more context into the trace details with some custom instrumentation.

## A request from marketing
The marketing team and social media PR team are working together on the launch of a new Stetson hat collection for Hipster Shop. The have tapped your team to best identify where ad dollars should be spent across the Unites States. The teams would like to know where orders are being shipped to so they can begin targetting specific states with social media ads. 

## Your plan of action
You query the data coming into Hipster Shop using the query below but get nothing. Argh! 
![Cursor_and_shippingservice___shippingservice___New_Relic_One.png](images/Cursor_and_shippingservice___shippingservice___New_Relic_One.png)

Next, you look up and down the many functions in the distributed trace you looked at earlier in the lab. Still no attribute for State, City, or anything simlar to help find the location of shipping orders. What do you do? Order another $7 cappuccino? No! You decide roll up your sleeves a little more to try and figure this out. 

## Fixing this issue
Realizing that you can't locate or query by the attribute "state" you know that your next step is to input some custom instrumentation code into the `shippingservice/main.go` file or you risk the chance of hipster's heads across the country not being accompanied by a Stetson hat :scream: 

At this point, your system of collecting telemetry data (OpenTelemetry) is lacking the attribute(s) needed to collect the data you want. You will need to discover a way to import and add those attribute(s) to a span.


*^^ I'm trying to find a way for someone to figure out how to do this on their own but it seems to difficult still. Perhaps there is a URL we can provide to help in this process?*

## Moving forward in the workshop
Once you have identified the issue, be sure to document your process. When that is done, you are ready to move onto the next excercise in this workshop [Part 3: Building Spans](https://github.com/Bijesse/otel-workshop/blob/main/Part_3-Building-Spans.md)