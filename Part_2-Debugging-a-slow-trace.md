# Part 1: Debugging a slow trace

In this exercise you are going to take a look at a consistently slow experince that all customers are having. You will then use New Relic to identify and resolve this issue.

## Locating the frontend issue

At this point, the Hipster Shop help line has been receiving countless calls for orders with complaints from angry hipsters who can't use the website to make their order. Several of the complaints state they have no issue loooking for the latest trends in clothing across multiple pages but their tiny attention spans are put to the test when they find themselves waiting for multiple seconds for pages to load when they are ready to view their cart and make an order.

You decide to visit the website yourself to see what is going on. to do this, follow these steps and make note of any issues that occur along the way.

1. Go to [localhost:3000](*) 
2. Add at least one item to your shopping cart
3. Complete the purchase process to make an order online

## Find the problem microservice
Now that you have experienced the issue on the front end, it is time to dig into New Relic to identify the root cause. Hipster Shop is built on a variety of microservices while should help organize your search. But several microservices are interacting with the front end at the same time. To begin your Observability sluething, identify the microservice that seems significantly slower than the others.

## Following a trace
Once you have identified the slower microservice, make use of distributed tracing in New Relic to find the specific function causing the slow page load times.

## Dive into the code
At this point in your sleuthing, you should have a hint or two regarding where you might find the issue. Try and locate the issue in the code of this application and remove it. 


## Moving forward in the workshop
Once you have identified the issue, be sure to document the process you completed using the companion guide. When that is done, you are ready to move onto the next excercise in this workshop [Part 3: Building Spans](*)