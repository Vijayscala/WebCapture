# When to Mock

_Captured: 2015-10-17 at 21:56 from [blog.8thlight.com](http://blog.8thlight.com/uncle-bob/2014/05/10/WhenToMock.html)_

A mock object is a very powerful tool, providing two major benefits: isolation and introspection. But like all power tools, mocks come with a cost. So where and when should you use them? What is the cost/benefit trade off? Let's look at the extremes.

## No Mocks.

Consider the test suite for a large web application. Let's assume that test suite uses _no_ mocks at all. What problems will it face?

  * The execution of the test suite will probably be very slow: dozens of minutes -- perhaps hours. Web servers, databases, and services over the network run thousands of times slower than computer instructions; thus impeding the speed of the tests. The cost of testing just one `if` statement within a business rule may require many database queries and many web server round-trips. 

  * The coverage provided by that test suite will likely be low. Error conditions and exceptions are nearly impossible to test without mocks that can simulate those errors. Functions that perform dangerous tasks, such as deleting files, or deleting database tables, are difficult to safely test without mocks. Reaching every state and transition of coupled finite state machines, such as communication protocols, is hard to achieve without mocks.

  * The tests are sensitive to faults in parts of the system that are not related to what is being tested. For example: Network timings can be thrown off by unexpected computer load. Databases may contain extra or missing rows. Configuration files may have been modified. Memory might be consumed by some other process. The test suite may require special network connections that are down. The test suite may require a special execution platform, similar to the production system. 

So, without mocks, tests tend to be slow, incomplete, and fragile. That sounds like a strong case for using mocks. But mocks have costs too.

## Too Many Mocks

Consider that same large web application, but this time with a test suite that imposes mocks between all the classes. What problems will it face?

  * Ironically, some mocking systems depend strongly on _reflection_, and are therefore very slow. When you mock out the interaction between two classes with something slower than those two classes, you can pay a pretty hefty price.

  * Mocking the interactions between all classes forces you to create mocks that return other mocks (that might return yet other mocks). You have to mock out all the data pathways in the interaction; and that can be a complex task. This creates two problems.

    1. The setup code can get extremely complicated.
    2. The mocking structure become tightly coupled to implementation details causing many tests to break when those details are modified.  

  * The need to mock every class interaction forces an explosion of polymorphic interfaces. In statically typed languages like Java, that means the creation of lots of extra `interface` classes whose sole purpose is to allow mocking. This is over-abstraction and the dreaded "design damage".  


So if you mock too much you may wind up with test suites that are slow, fragile, and complicated; and you may also damage the design of your application.

## Goldilocks Mocks

Clearly the answer is somewhere in between these two extremes. But where? Here are the heuristics that I have chosen:

  * **Mock across architecturally significant boundaries, but not within those boundaries.**  


For example, mock out the database, web server, and any external service. This provides many benefits:

  1. The tests run much faster.
  2. The tests are not sensitive to failures and configurations of the mocked out components.
  3. It is easy to test all the failure scenarios generated by the mocked out components.
  4. Every pathway of coupled finite state machines across that boundary can be tested.
  5. You generally don't create mocks that return other mocks, so your setup code stays much cleaner.

Another big benefit of this approach is that it forces you to think through what your significant architectural boundaries are; and enforce them with polymorphic interfaces. This allows you to manage the dependencies across those boundaries so that you can independently deploy (and develop) the components on either side of the boundary.

This separation of architectural concerns has been a mainstay of good software design for the last four decades at least. Good software developers pursued such separation long before Test Driven Development became popular. So it is ironic that striking the right balance of isolation and speed in our tests is so strongly related to this separation. The implication is that good architectures are inherently testable.

  * **Write your own mocks**.

I don't often use mocking tools. I find that if I restrict my mocking to architectural boundaries, I rarely need them.

Mocking tools are very powerful, and there are times when they can be quite useful. For example, they can override sealed or final interfaces. However, that power is seldom necessary; and comes at a significant cost.

Most mocking tools have their own domain specific language that you must learn in order to use them. These languages are usually some melange of dots and parentheses that look like gibberish to the uninitiated. I prefer to limit the number of languages in my systems, so I avoid their use.

Mocking across architectural boundaries is _easy_. Writing those mocks is _trivial_. What's more, the IDE does nearly all the work for you. You simply point it at an interface and tell it to implement that interface and, voila!, you have the skeleton of a mock.

Writing your own mocks forces you to give those mocks _names_, and put them in special directories. You'll find this useful because you are very likely to reuse them from test to test.

Writing your own mocks means you have to _design_ your mocking structure. And that's never a bad idea.

When you write your own mocks, you aren't using reflection, so your mocks will almost always be extremely fast.

## Conclusion

Of course your mileage may vary. These are _my_ heuristics, not yours. You may wish to adopt them to one extent or another; but remember that heuristics are just guidelines, not rules. I violate my own heuristics when given sufficient reason.

In short, however, I recommend that you _mock sparingly_. Find a way to test -- _design_ a way to test -- your code so that it doesn't require a mock. Reserve mocking for architecturally significant boundaries; and then be ruthless about it. Those are the important boundaries of your system and _they need to be managed_, not just for tests, but for everything.

And write your own mocks. Try to depend on mocking tools as little as possible. Or, if you decide to use a mocking tool, _use it with a very light touch_.

If you follow these heuristics you'll find that your test suites run faster, are less fragile, have higher coverage, and that the designs of your applications are better.

Robert Martin (Uncle Bob) is a Master Craftsman. He's an award-winning author, renowned speaker, and has been an uber software geek since 1970.