# Lab 2: Debugging a slow trace

For the remainder of this workshop, you will step into the shoes of a DevOps engineer at the popular online store Hipster Shop. In your role, you are often tasked with using the power of observability that New Relic provides to resolve problems and create proactive solutions. 

## Locating the frontend issue

Starting around 10-10:30AM today, the Hipster Shop social media PR team has been busy locating and responding to countless Tweets and TikToks from hipsters starting their morning expecting to spend money. Their angry hipster complaints are related to issues using the website to make an order. Several of the complaints state they have no issue looking for the latest trends in clothing across multiple pages but their tiny attention spans are put to the test when they find themselves waiting multiple seconds for pages to load when they are completing their shipping details to make an order.

## Find the problem microservice
Now that you are aware of the issue users are experiencing on the front end, it is time to dig into the data in New Relic to identify the root cause. Hipster Shop is built across a variety of microservices which should help organize and contain your search. To begin your observability sleuthing, identify the microservice that seems significantly slower than the others. **Hint: Response Time!**

## Following a trace
Once you have identified the slowest microservice, make use of [distributed tracing](https://newrelic.com/blog/how-to-relic/distributed-tracing-general-availability) in New Relic to find the specific function causing the slow page load times.

## Dive into the code
At this point in your sleuthing, you should have a hint or two regarding where you might find the issue. Try and locate the issue in the code of this application and remove it using comments.

**Hint: Once you have identified the problematic service, the issue is locating in the main.go file of that service. This is the only file you will be required to edit while completing labs 2-4**

## Alerting on this issue
At this point, you have resolved the issue but you have some concern that a developer might reproduce the issue during an upcoming sprint. To account for this, create an alert that will notify you if the service that was causing the slowness in this lab becomes slow again.

## Moving forward in the workshop
Once you have identified the issue and created an alert for future instances of it, be sure to document the process you took to locate and resolve this issue, and store the distributed trace permalink for safekeeping. When that is done, you are ready to move onto the next lab in this workshop [Lab 3: Building Spans](lab_3-Building-Spans.md)
