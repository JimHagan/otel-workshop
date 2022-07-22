# Lab 3: Building spans

In this lab you are going to build individual spans so that the information provided to you in New Relic can better pinpoint the problem

## Speaking with your developer
In the previous excercise, you were able to leverage New Relic to locate the problem. However, it took you much longer than you would have hoped to find a command that one of your colleagues probably forgot to remove while debugging an issue that was clearly not meant for production. :facepalm: 

You show a developer on your team the New Relic permalink showing the distributed trace from Part 2 of this lab. You task them that to create a solution that would allow you to get closer to being able to identify the exact line of code that is causing an issue or delay in this microservice. 

Your developer sent you a few code snippets at 9pm last night since they have a planned PTO for the next couple of weeks. Their message is below.


> Hey there,  
> 
> These updated code blocks will generate individual spans to fix your problem. Add them to each function along with the sleep commands you found earlier (to reproduce the issue you had previously) and you should see how I fixed the problem.
> 
> If you have any questions while I'm gone... good luck! You'll figure it out.
> 
> Cheers,  
> Your Favorite Dev


```
func (s *server) GetQuote(ctx context.Context, in *pb.GetQuoteRequest) (*pb.GetQuoteResponse, error) {
	...	
		// 1. Generate a quote based on the total number of items to be shipped.
	quote := CreateQuoteFromCount(0, ctx)
	...
}
```


```
func CreateQuoteFromCount(value float64 , ctx context.Context) Quote {
	ctx, childSpan := tracer.Start(ctx, "CreateQuoteFromCount")
	...
	return CreateQuoteFromFloat(float64(rand.Intn(100)), ctx)
}
```

```
func CreateQuoteFromFloat(value float64 , ctx context.Context) Quote {
	ctx, childSpan := tracer.Start(ctx, "CreateQuoteFromFloat")
	defer childSpan.End()
	...
}
```
## Your task
Read the message from the developer so that you can update the code in the `shippingservice/main.go` file. After you have updated the environment, head back to New Relic to see how the data coming in from the distributed trace has changed. Document your findings.



## Moving forward in the workshop
Once you have identified the benefit(s) of including spans, be sure to document your process. When that is done, you are ready to move onto the next lab in this workshop [Lab 4: Adding Span Attributes](lab_4-Span-Attributes.md) 