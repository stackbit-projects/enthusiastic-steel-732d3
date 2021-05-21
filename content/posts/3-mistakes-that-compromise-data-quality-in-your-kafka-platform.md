+++
content_img_alt = ""
content_img_path = "/images/robin-pierre-dpgpoiuiixk-unsplash.jpg"
date = 2021-04-30T02:06:00Z
excerpt = "What does it look like, is it consistent, is it even usable are all questions you need to ask about the quality of the data in your Kafka deployment. Here are 3 mistakes to avoid to ensure you always have high quality data flowing through your Kafka platform."
layout = "post"
subtitle = ""
thumb_img_alt = ""
thumb_img_path = "/images/robin-pierre-dpgpoiuiixk-unsplash.jpg"
title = "3 mistakes that compromise data quality in your Kafka platform"
[seo]
description = ""
extra = []
robots = []
title = ""
type = "stackbit_page_meta"

+++
Kafka, as a distributed event streaming platform, can support millions, billions and even trillions of messages a day. With that much data flowing through a platform how do you know how useful any of that data is? What does it look like, is it consistent, is it even usable are all questions you need to ask about the quality of the data in your Kafka deployment. Here are 3 mistakes to avoid to ensure you always have high quality data flowing through your Kafka platform.

**_No.1 - Platform engineers are not data domain experts_**

Centralising administration of a Kafka platform often results in platform engineers creating topics and schemas on behalf of other teams. Not only does this create a bottleneck in the process it forces the platform engineers to quality control every submission.

They may need to check for duplicates or they may need to check for compliance with corporate standards or legal requirements amongst other things. They won't know the details of your data domain and won't be able to check if your schemas make sense or that they conform to any enterprise data model.

These checks are usually imposed by other parts of the business, like legal, security or risk. As a result the platform engineers become accidental gatekeepers of the Kafka capability. They front up the bottleneck but ultimately that's not their 'day job'; platform engineers are not data domain experts. The quality of data doesn't improve AND the quality of the platform itself suffers.

**_No.2 - Not enforcing use of a schema registry from the start_**

In my opinion, schemas should not be optional for the majority of Kafka use cases. Defining a schema for each message not only provides clear documentation for any consumers but importantly allows the platform to enforce conformance to that schema rejecting any bad data.

Data quality instantly improves

Assuming you've set up a schema registry and the brokers are configured correctly, then as a consumer of a Kafka topic that enforces schemas you can be confident that every message you receive will be of the same quality.

> Schemas move data quality to the left

A secondary benefit of enforcing schemas for every producer is that the data quality 'moves left'. It is frequently the job of data wranglers in the analytics space to clean up and conform data to common standards so it all makes sense when queried together. Conforming data at the point it is published frees up that analytics processing to derive better customer insights.

**_No.3 - Not automating the creation of topics and schemas_**

Remember that platform engineers are not data domain experts? That's because Kafka topics and message schemas are domain specific and should be owned by the team delivering that capability (this continues to be true for automatically created topics in the Streams API and ksqlDB).

> Automation empowers teams to own their data

Providing an easy and consistent way to automatically create topics and schemas is an essential part of empowering teams to own their data. If there is no automation then, again, the data quality suffers with inconsistent application of standards.

Equally, automation lowers the barrier to entry. If it's easy to do then people will want to do it.

Making the process difficult puts people off and forces them to make shortcuts, again compromising the quality of data.

The Kafka platform provides programmatic APIs and SDKs that make it possible to automate much of the cluster administration so there's really no reason not to automate.

These 3 mistakes combined result in streams of bad data that will ultimately need to be cleaned up by multiple consumers to be of any use. Putting a little bit of thought and effort into roles, ownership, schemas and automation can make a huge difference to the quality of your Kafka event streams. Instead of getting overwhelmed and losing control as data streams hurtle past you at a hundred miles an hour, take a breath and inject some mindfulness into your event streams.

Connect with me to learn more about how you can improve the data quality of your Kafka event streams.