# Why GraphQL?

What does the perfect API look like?
It should be efficient, fast and easy to use for our users
and it should be equally efficient, fast and easy for us to develop.

To be fast and efficient we need to carefully choose the data that we return from our API.
If we return data that the user does not use or need we are not as efficient as we could be.

Every byte that we make our users download will literally cost time
and - especially on mobile network plans - money.

**An API is about its users**. We as developers of an API should always keep that in mind.
It does not matter whether it is directly consumed by a customer's device or if it's consumed by another micro service or application.
At the end of the day, our API is an interaction with others and it's our responsibility to make that as good and joyful as we possibly can.

Efficiency and fastness will improve the overall performance of our application - which numerous studies have proven to be
the number 1 factor for good user experience. Improving on these factors will literally increase our revenue.
And hey - I'm more likely to keep using an app that respectfully uses my data plan.

An easy to use API can greatly decrease the time that is required to innovate on new features.
Developers will have a much nicer time implementing a feature and we can roll them out more frequently to our customers. And the easier an API is to use, the lower the risk of
introducing bugs is.

An API is about it's users.

## Knowledge is everything

You're probably familiar with the phrase _Knowledge is power._
Or as I like to put it _Scientia potentia est_ because I like to fancy myself with latin quotes I copied from Wikipedia.

It truly is.
If you know what the users of your API want you can model it in a way that is
efficient, fast and easy to use.

But how do you know what data the users want?
If the only user of your API is your co-worker in the next cubicle you can ask him.
But what if you have an API that is consumed by multiple users? Do you know them all?
Do they all have the same exact data requirements?

How could we model an API that is efficient for every user we have?

One option is to handcraft an API for each user.
Depending on the number of different users you have this might sound like a suitable solution.

But every time one of the users changes his data requirements we need to update their custom API.
Actually, we're now limiting the speed of our users' innovations by how quickly we can customize it.

Custom APIs for every client would work perfectly if the cost
of keeping them up and running wouldn't be so high.
Or in the case of not knowing our users at all - even possible.

### REST

So what if we created a couple of small APIs that each return only a small subset of our data instead?

Now if you've heard of REST this might sound familiar to you.
A REST API consists of multiple endpoints.
An endpoint is just an URL which returns a fixed structure of data. A resource.

The point of having multiple endpoints is that we allow our users to request our data more granularly so we don't serve them with too much unnecessary information.
This means we should keep our endpoints small and concise.

Deciding which data belongs to a certain resource is up to the API developer.
There are tradeoffs. If an endpoint is really small it's more efficient since it doesn't send
a bunch of unused information. But chances are high that not all the required data is returned by that one endpoint which means the user has to request multiple endpoints. This is called _underfetching_.

If you provide more data in a single endpoint than chances are high that there's a bunch of unused data. This is called _overfetching_.

**Creating endpoints is a tough challenge**.
This is especially true for relational data. And to be frank, any data is relational.

A house has owners. Owners have family and friends which each have their own houses.
Houses belong to a street. Streets to a city and so on.
The world is literally a graph. And any of us is just a small node on it.

This does not seem really romantic, does it?
But the upside to that is that we are technically all friends with Kevin Bacon - at least to some [degree.](https://en.wikipedia.org/wiki/Six_Degrees_of_Kevin_Bacon)

Think about it for a minute. How would you structure your API for this?
Would you create an endpoint for a house? Will it include the information about the owner?
What about their families and their houses? Where do you draw the line?

We don't know what our users need from our API so it's hard to come up with a solution.
Smaller endpoints are more efficient but require multiple requests.
Bigger endpoints save us roundtrips but could send too much data.
Either way is not ideal. It's a compromise.

Phew. If only we knew better.

REST started with a good thought. Creating multiple endpoints and make users ask for specific slices of data.

However, relying on HTTP requests to select slices of data is not an optimal solution. It can be hard and tedious to orchestrate the requests. The users need to find out which requests can be sent concurrently and which requests needs to be performed sequentially.
Sequential requests create a critical path and can dramatically slow down the user experience because we if one request takes longer the whole chain is delayed.

Making an HTTP call also comes with a latency. We need to open a connection.
Perform an SSL handshake and close the connection. All of that is time-consuming.

## Just tell us

We should think about graphs, not endpoints.
Endpoints force us to make decisions about how our API is consumed.

What we need is a way for our users to tell about how they plan to use our API.
A way to specify which data they require.
That's what GraphQL is about. It's a language to formulate those needs.

It's exactly what SQL is for our databases.
The database doesn't know which data it should return so we need to formulate a query with all of our requirements.

By using GraphQL we shift the responsibilities. The API developer is not in charge of deciding which data gets sent to the user anymore. He's responsible for defining what data is available and how this data can be accessed. He's in charge to create the graph.

It's the users' job to look at the available data and pick the one they. After all, they know best.
In a way, we enable them to create their own handcrafted, perfectly tailored API.
And since the users can create it themselves, we're no longer a bottleneck for innovation.

That's efficiency and fastness at work.
For our users as well as ourselves.

GraphQL is about communication. It allows API developers to specify which data is available and
API users to specify which data they need. This improves the way we use our API and
it enables us to improve our tooling along with it.

We can get insight on how our API is used,
which part of the data might became irrelevant and can be removed and even
give users an estimate on how long it will take for their data to download.

We can provide users of our data with autocomplete suggestions for their IDE,
validate their queries at build time and even generate code for them.

All of that is possible because GraphQL allows developers to communicate
their needs by using an expressing, yet simple to learn language.

GraphQL is not a revolution. It's an evolution. It's the next logical step when you think
about API development.
