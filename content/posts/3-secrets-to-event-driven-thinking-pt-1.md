+++
content_img_alt = ""
content_img_path = "/images/volodymyr-hryshchenko-v5vqwc9gyeu-unsplash.jpg"
date = 2021-05-14T01:23:00Z
excerpt = "I'm posting short dialogues that highlight the 3 most common challenges I see in understanding event-driven thinking. No. 1 - Commands dressed as events"
layout = "post"
subtitle = ""
thumb_img_alt = ""
thumb_img_path = "/images/volodymyr-hryshchenko-v5vqwc9gyeu-unsplash.jpg"
title = "3 secrets to event-driven thinking - Pt 1"
[seo]
description = ""
extra = []
robots = []
title = ""
type = "stackbit_page_meta"

+++
The idea of the event-driven architecture (EDA) has been around for a while now. Indeed it was back in 2005 that Martin Fowler was writing about the concept of [**event sourcing**](https://martinfowler.com/eaaDev/EventSourcing.html) that now underpins event streaming platforms like Apache Kafka.

> _Capture all changes to an application state as a sequence of events. -_ Martin Fowler

The thing is, I still see very clever software professionals seemingly struggling with the concepts of EDA. Those with a good grounding in domain-driven design seem to find the leap easier. Those coming from a starting point in REST APIs, large enterprise database solutions, or even 12-factor applications may find event thinking at odds with what they already know.

I'm posting short dialogues that highlight the 3 most common challenges I see in understanding event-driven thinking. Here's the first one.

**_No. 1 - Commands dressed as events_**

An event-driven architecture means I can't call APIs anymore (not entirely accurate but it's a great starting principle) so I'll use an event to tell another service or system that it needs to do something.

Ok. Great. So an event is supposed to be a record of fact, of something that has already happened - how can an event tell another system it needs to do something?

Oh, well the event just records the fact that I instructed the other system to do something - a 'systemCalled' event.

And what happens then?

Well I wait for the other system to send me an event back with the result.

What you've just described is a synchronous exchange using events as commands in an API-centric way - you've just swapped the API call for a couple of events. Unfortunately that's not an event-driven architecture.

Think of your events as asynchronous progress updates instead. Publish the result of some processing you've just completed and stop expecting a response.

But how do I tell the other system it needs to do something?

The other system could subscribe to the event you've published and asynchronously decide it needs to do some work based on that event. The outcome is the same with the crucial difference being that you no longer care if the other system does that work or not.

Alternatively you could just call the API if the other system actually sits in the same bounded context. APIs are still great for commands.

If neither of those options look viable then it's likely the scoping of the services and bounded contexts isn't quite right. Event-driven thinking forces you to re-evaluate these boundaries and identify well bounded microservices.

Always think carefully about whether you need a command or an event and then treat it appropriately. Don't dress up a command as an event just because you've been told to use events.