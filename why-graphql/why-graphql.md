# Why GraphQL?

So what does the perfect API looks like?
It should be efficient, fast and easy to use for our users
and it should be equally efficient, fast and easy to develop for us.

To be fast and efficient we need to carefully choose the data that we return from our API.
If we return data that the user does not use or need we are not as efficient as we could be.

Every byte that we make our users download will literally cost time
and - especially on mobile network plans - money.

**An API is about its users**. We as developers of an API should always keep that in mind.
It does not matter whether it is directly consumed by a customer's device or if it's consumed by another micro service or application.
At the end of the day, our API is an interaction with others and it's our responsibility to make that as good and joyful as we possibly can.

Efficiency and fastness will improve the overall performance of our application - which numerous studies have proven to be
the number 1 factor for good user experience. Improving on these factors will literally increase our revenue.
And hey - I'm more likely to keep an app that respectfully uses my data plan.

An easy to use API can greatly decrease the time that is required to innovate on new features.
Developers will have a much nicer time implementing a feature and we can roll them out more frequently to our customers.

An API is about it's users.

## Knowledge is everything

You're probably familiar with the phrase _Knowledge is power._
Or as I like to put it _Scientia potentia est_ because I like to fancy myself with latin quotes I copied from Wikipedia.

It truly is.
If you know what the users of your API want you can model it in a way that is
efficient, fast and easy to use.

But how do you know what the users want?
If the only user of your API is your co-worker in the next cubicle you can ask him.
But what if you have an API that is consumed by multiple users? Do you know them all?
Do they all have the same exact data requirements?

How could we model an API that is efficient for every user we have?
Well if we know them and can ask for their needs we can handcraft an API for every single user perfectly suited for his needs.
That will make it efficient for them, but maintaining multiple APIs that we need to adjust
whenever a user changes his requirements seems like an exhausting solution for us.

And if we don't know all of our users we will never be able to craft an API especially for their needs.

What if we created a couple of small APIs that each return only a small subset of our data instead?
This way we can ask our users to tell us which slice of the data they are interested in by calling the corresponding API.

Now if you're familiar with REST this might sound familiar to you.
A REST API consists of multiple endpoints which each return a set of related data.

Our users tell us what slice of data they need and we serve only that slice.
Oh. That knowledge.

Yeah yeah, it's not perfect. We only know which chunk of data they are interested in,
it's not perfectly granular, but it works. At least we optimized a bit without making
it too hard to maintain our API.

Well, it's true that our users are now responsible for gathering together all the information they need. Probably make a few API calls which can take up some time but at least they can tell us what they need. It's a little bit harder to use and it can be slower if you need a lot of different slices but what are the options?

APIs are about its users. So who does know best which data is needed?
Obviously, it's the user. Not the API developer.

We need our users to tell us which data they need so we don't have to make assumptions.
That's the thing about assumptions. They're usually wrong anyway.

REST started with a good thought. Creating multiple endpoints and make users query for their needs slices of data will give us insight on which data our users need.

However, querying slices of data by making multiple HTTP requests can actually slow us down. It's can be hard and tedious to orchestrate the requests. For each slice of data, we need to connect to the server, which comes with some overhead and latency which eventually leads to a slower app.

## Just tell us

What we need is a way to tell our API what data we need without relying on HTTP endpoints.
That's what GraphQL is about. It's a language to formulate that needs.

It's not a revolution. It's an evolution. It's the next logical step when you think
about API development.

By using GraphQL we shift the responsibilities. Before, the API developer was in charge of deciding what data gets sent to the user. Now his responsibility is to define what data is available and how this data can be accessed.

It's the users' job to decide which data he needs and to formulate the query. After all, they know best.
In a way, we enable them to create their own handcrafted, perfectly individualized API.

That's efficiency and fastness at work.
For our users as well as ourselves.

GraphQL is about knowledge. It improves the way we use our API and
it enables us to improve our tooling along with it.

We can get insight on how our API is used,
which part of the data might became irrelevant and can be removed and even
give users an estimate on how long it will take for their data to download.

We can provide users of our data with autocomplete suggestions for their IDE,
validate their queries at build time and even generate code for them.

All of that is possible because GraphQL allows developers to communicate
their needs by using an expressing, yet simple to learn language.
