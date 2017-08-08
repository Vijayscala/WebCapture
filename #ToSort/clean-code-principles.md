# Clean Code Principles

_Captured: 2017-01-30 at 01:09 from [dzone.com](https://dzone.com/articles/clean-code-principles?utm_content=buffer348d5&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer)_

Learn more about [how DevOps teams must adopt a more agile development process](https://dzone.com/go?i=148026&u=https%3A%2F%2Fwww.ca.com%2Fus%2Fcollateral%2Febook%2Fexploring-the-tools-that-make-agile-parallel-development-possible.register.html%3Fmrm%3D540542%26cid%3DNA-DSP-ABUS-ACM-000195-00001285-000000492%26aid%3D00702), working in parallel instead of waiting on other teams to finish their components or for resources to become available, brought to you in partnership with [CA Technologies](https://dzone.com/go?i=148026&u=https%3A%2F%2Fwww.ca.com%2Fus%2Fcollateral%2Febook%2Fexploring-the-tools-that-make-agile-parallel-development-possible.register.html%3Fmrm%3D540542%26cid%3DNA-DSP-ABUS-ACM-000195-00001285-000000492%26aid%3D00702).

## What Is Clean Code?

[Clean code](http://cleancode.io) is a philosophy that I follow when I code. Actually, to me, it feels more like a religion than a philosophy! It's the idea that your code should be precise and as close to perfect as possible. If you have more code than you need, it shouldn't be there. There shouldn't be anything superfluous, and I go so far as to say that there shouldn't even be superfluous whitespace. You want your code to be as efficient, readable, and maintainable as possible, and instead of only "solving the problem." I always put in the extra time to also focus on the design of my code.

It all started in 2001 when I was reading the _Pragmatic Programmer_ by Andy Hunt and Dave Thomas. I read statements (like, "never accept a broken window,") that resonated with me.

It's very easy to visualize this. Imagine that you have a house and it starts to fall apart because there's no blueprint to fix it, and it gets worse and worse until the roof caves in. Or, you have a shopping cart that's been abandoned on the street corner and that people start throwing their trash into. Pretty soon, the whole cart is full of garbage that then spills over. In both cases, if you don't set clear boundaries and rules, you'll run into problems in the long term. I've joined new companies before where the teams have created dirty code, and it's not fun to work there. I realized that when people start off lazy with no sense of responsibility for their code, it very quickly starts to decay. They then end up having to spend hours and hours fixing and refixing the lines every time a change is made somewhere else. Nobody needs code like that.

I refer to myself as a pragmatic perfectionist. It means that on one hand, I deal with problems that exist in a specific situation in a reasonable and logical way instead of just depending on vague ideas and theories. On the other hand, I want my code to be perfect as possible the first time, not because I like wasting time, but because I'm thrifty enough to see that it'll save me way more time later on.

![Clean Code Craftsman](https://dzone.com/storage/temp/3901399-craftsman.jpg)

> _Clean Code Craftsman_

## How to Implement Clean Coding Design

So, how does one create clean code? Well, first of all, you can't think of your project as a coding project; you have to think of it as a designing and planning process. Developers often rush into the code because they feel pressure from their managers or whomever to get the job done quickly. In contrast, a clean coder makes sure he fully understands the problem before beginning to code. Imagine you're building a house, but you decide to only build a flimsy foundation. If you then decide to expand the house, you're going to have to waste more time and money rebuilding the foundation. That's why, to me, the first step in the process is to have a discussion with the client to find out exactly what he or she wants.

That leads me to the next step for clean code: creating this common language, or a "ubiquitous language," if you follow the ideas of [Domain-Driven Design](https://en.wikipedia.org/wiki/Domain-driven_design). The wording of code is very important because you want your variable names, class names, and package names to make sense no matter who is looking at the code. Now, some developers will say, "For God's sake, let's just use some stupid name and change it later."

While this may appear to be the quickest solution, the team, or even the same developer who wrote it, might get lost in these directionless names. Every abstract word in the code might give different team members different concepts as to the direction of the project. If I'm thinking of programming a pear and you're thinking of programming an apple, we'll end up with a useless apple-pear hybrid.

If everyone involved, from clients through to developers, communicates well during the design process, we initiate this common "ubiquitous language" that evolves with the project. The goal is a complete, understandable program, written by an entire team, yet looking as if it has been written by an individual. It should consist of simple elements that join together to communicate complex ideas. We should avoid terms that are ambiguous and don't convey proper understanding. Communicating in this manner will help us prevent problems, rather than having to fix them later. Now, we can confirm whether the client wants an apple or a pear, resulting in a satisfied client at the end. That extra hour spent on discussions at the beginning can really assist the direction of a project and save many hours later on.

## Estimation Gambling

One of the difficulties with clean coding is estimating your timeframe. A lot of developers have a fear of being honest with their managers, which is why I think it's important to trust your manager. Say you have a gut feeling that a project will take ten days, but you're scared to say "ten days," so you figure, "Well, if I work really hard and I work extra hours and if everything works fine, I should be able to make this in eight days." I call this estimation gambling. So, you've decided on a timeframe and you go to your boss or client and you say, "I'll make it in eight days." Guess what? Many managers will come back to you and say, "I'll give you four!" So, a project that you know will probably take ten days, if it's bug-free, is now getting barely any time, and now you're rushed and you can't make the code as clean as you should.

Usually, I take everything into account. If I feel like a project will take ten days, I usually tell my client fifteen. That doesn't mean I spend the first five days lounging around. I try my hardest to finish that project based on my gut feeling, but it often happens that my clients will change requirements, or maybe my initial design won't work out, so I'll need those extra five days.

This is a hard thing for a developer to do, especially when your co-worker claims he or she can do it in half the time. Sure, maybe they'll get this job, but when the result is crap, you'll get the next one. On a flexible team, your boss might let you have extra time if you don't finish on time, but that's also gambling. A client will rarely be as forgiving. Never gamble with how much time you'll take. You have to have trust in yourself and in your knowledge.

To me, being a software craftsman is about having a focused attitude and about taking responsibility for your code, your job, and your time. So, from beginning discussions to end results, your one focus should be on maintaining your own high standards and creating the best possible product for your client.

## System Design

OK, so now that we have our vision, our common language, and our timeframe, we can begin to actually plan out our code. The way I do this is by drawing boxes on a white board that represents our system and how different components of our system will work together. The goal of this is to visualize how our system will function and to discuss the most efficient way to have our components interact. When you find complexity in your design, look for ways to simplify -- complex areas are hotbeds for bugs and code breaking.

Now, you've got your design, but what about your neighbor? His idea for developing the same system might be completely different than yours, and this is where we have more discussion. Working in small groups, I always believe developers should debate and discuss their system. This helps to make the system more efficient and effective. It also helps to maintain a unified vision for the code and keep team spirits up as everyone is working together.

I like to take these boxes as an opportunity for further communication with the client. They don't usually understand code, but they do understand boxes and drawings with business terms in them. You can ask them, "Is this what you were thinking of?" and have them participate in the process. This is one of the most powerful aspects of system design that many developers fail to utilize because even people who don't understand code can still understand the overall concept of the design.

Don't be overly concerned when disagreements amongst the team and between the team and client arise. A disagreement is a great indicator that further refinements or adjustments are needed, and should be seen as a chance to improve the result, rather than as a threat. They just mean that you need to talk more until you come to a common understanding. A lightweight, team-based approach with open discussion is key here. Companies with flat hierarchies have an easier time promoting this type of discussion. Always get the client involved in the discussion as early as possible. Sometimes, the reason for the difference of opinion might be that the client is unaware that their choices may lead to bad performance, difficult maintainability, or high costs. So, ask them, "Do we really need this feature now? If we do, can we simplify it?"

From the other side, developers are often unaware of the compelling business reasons that may have led the client to ask for the added complexity. Often, clients want a lot of unnecessary features, and the developers try to provide them. While I believe that the developer's job is to enable the client, you would not be doing the client a favor by just following his or her instructions blindly without challenging those that appear impractical to you. Differences need to be thrashed out with lots of respect and trust on both sides. If you manage to put ego aside and facilitate this process, the results are bound to be fruitful for both sides. Both sides must keep asking questions and challenging each other's point of view until they come to a common understanding. This will highly increase the chances of producing a successful product that does exactly what the client needs it to do.

On top of this, one of the things I often hear developers say is, "Oh, let's add some extra feature because we might need it in the future." Never do that. I used to do that, but I've realized it's a useless waste of time. Worse than that, it's actually harmful. When you over-complicate the code by adding extra features, you are making the code harder to read, understand, maintain, and test. By doing this, you're inviting bugs into your code. So, these unnecessary extra features are truly evil! You don't know the future, and nine out of ten times your assumption will be wrong. Even if you were right that a feature would be necessary later, it might only be needed two years down the road, and by then, you might have found a better way to do it.

If you're building a house and you decide to add an extra room once the foundation has been laid, it's going to cost huge amounts of time and money. On the other hand, software is different. Software can be changed iteratively for a much lower cost. Changing it is not easy, but it's certainly a lot easier than adding rooms to a house. The better the software has been built, the easier and therefore cheaper it will be to make changes. As a programmer, simplistic code is what you should always strive for.

## Writing the Code

Finally, after all of this designing, you can start coding. As you can see, there is a lot going on before the coding even starts, and that's one of the differences between clean code and dirty code: the design behind it.

A misunderstanding many people have is that because of all the time they spent on design, their code will be better right away and it can just be written in a straightforward way. That isn't the case. You should still stay regimented and carefully craft and test your code, even if you think your design is flawless. There is much more to software development than just doing a quick design and writing a few lines of code.

In an ideal situation, you should start with tests. If possible, I recommend using Test-Driven Development, TDD. Start off with an integration or acceptance test that fulfills a concrete business goal, and then follow that with many smaller unit tests. You should write the code after you write the test and then as soon as you have a green test, you can restart and refactor your code.

This "test-first" approach is very challenging for an organization that does not have flat organizational structures. To be able to work like this, an organization needs to be based on open communication and an iterative experimental approach without a hierarchical, top-down management style. The managers need to fully trust their team and hand over responsibility to them. However, there is still a long way to go with implementing this approach in most companies, where there are still many fears and blockades to contend with. This approach remains in strong contrast to the hierarchical management culture still found in the majority of organizations today.

Because of this, we need to start with small steps, and hopefully, companies will evolve over time. One small step is to replace the "test-first" with a "test-last" approach -- what matters most, at the end of the day, is that the code is actually tested. The test will refine our requirements again and allow us to focus on the functionality of our code -- that is, its design and structure, rather than how it operates technically. A developer needs to remember that he or she is primarily coding for the business, and not for him or herself, so the wording needs to be very clear. A misunderstanding of any kind among developers is going to result in a bug. Granted, this kind of bug won't stop your code from working, but when another developer tries to use your methods in a way you hadn't intended, further bugs will result.

I usually compare writing code to writing a book. No author writes their book starting with chapter one, then moving on to chapter two, all in order, making each one perfect before starting the next. An author starts off with an outline, then starts improving every page, then revises again and again until finally, the book is perfect. In terms of coding, that means moving past the first green test and recognizing that the "but it works" philosophy isn't a good one. You have to improve on your code until it is perfect. You're not only testing to see if the code works; you're also testing to make it as clean and precise as possible.

**[You enjoyed reading this article? For more of this, sign up for my free Java Clean Code Course!**](http://cleancode.io/)

[Discover the warning signs of DevOps Dysfunction](https://dzone.com/go?i=148027&u=http%3A%2F%2Ftransform.ca.com%2Fpragmatic-guide-to-devops.html%3Fmrm%3D540542%26cid%3DNA-DSP-ABUS-ACM-000195-00001286-000000493%26aid%3D00702) and learn how to get back on the right track, brought to you in partnership with [CA Technologies](https://dzone.com/go?i=148027&u=http%3A%2F%2Ftransform.ca.com%2Fpragmatic-guide-to-devops.html%3Fmrm%3D540542%26cid%3DNA-DSP-ABUS-ACM-000195-00001286-000000493%26aid%3D00702).

### Like This Article? Read More From DZone