# Part 1: Debugging a slow trace

In this exercise you are going to take a look at a consistently slow experince that all customers are having. You will then use New Relic to identify and resolve this issue.

## Locating the frontend issue

At this point, the Hipster Shop help line has been receiving countless calls for orders with complaints from angry hipsters who can't use the website to make their order. Several of the complaints state they have no issue loooking for the latest trends in clothing across multiple pages but their tiny attention spans are put to the test when they find themselves waiting for multiple seconds for pages to load when they are ready to view their cart and make an order.

You decide to visit the website yourself to see what is going on. to do this, follow these steps and make note of any issues that occur along the way.

1. Go to [localhost:3000](*) 
2. Add at least one item to your shopping cart
3. Complete the purchase process to make an order online

## Following a trace
Now that you have experienced the issue on the front end, it is time to dig into New Relic to identify the root cause. Since Hipster Shop is built with multiple microservices you should be able to identify where the problem begins by observing a trace. 

**Your Task** Follow distributed trace to locate the microservice causing a slowdown on Hipster Shop. Then use this infromation to identify the exact line of code causing the issue. Resolve it and try to make an order again