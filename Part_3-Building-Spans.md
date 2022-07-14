# Part 3: Building Spans

In this exercise you are going to build individual spans so that the information provided to you in New Relic can better pinpoint the problem

## Speaking with your developer
In the previous excercise, you were able to leverage New Relic to locate the problem. However, it took you much longer than you would have hoped to find a sleep command that someone probably forgot to remove during the development stage. :facepalm: 

You show your developer the permalink showing the distributed trace from Part 1 of this lab and tell them that you want to get closer to being able to identify the exact line of code that is causing an issue or delay.

Your developer sends you a few code snippets at 9pm last night since they have a planned PTO for the next couple of weeks. Their message is below.


## Your task
Read the message from the developer to update the code in the `shippingservice/main.go` file. After you have updated the environment, head back to New Relic to see how the data coming in from the distributed trace has changed. Document your findings in the companion guide.



> Hey there,  
> 
> These code blocks will generate individual spans to fix your problem. Add them to each function along with the sleep commands (to reproduce the issue you had previously) and you should see how I fixed the problem.
> 
> If you have any quesitons while I'm gone... good luck! You'll figure it out.
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

## Moving forward in the workshop
Once you have identified the benefit from including spans, be sure to document the process you completed using the companion guide. When that is done, you are ready to move onto the next excercise in this workshop [Part 4: NAME](*)