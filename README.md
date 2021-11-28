# the philosophy of streamforthepeople

**streamforthepeople** is a **streamer website as a service**

This document discusses its philosophy. **TLDR**: see the [core principles](#core-principles)

## core principles

1. To decouple the streamer's audience from the stream service provider; henceforth, the **corporate decoupling principle**.
1. To transfer ownership of this service to the streamers, where it would be operated, managed, and governed by some democratic body of streamers, e.g. a "streamer's guild"; henceforth, the **ownership transfer principle**.

## disclaimers
While I did take a philosophy class in college (it was about data philosophy heh), I am only an amateur philosopher. As such, this document will likely lack some rigor and not fill in all the expected philosophical gaps; if you find anything of concern and would like to address it, please create an issue or pull request on this repo and we can discuss it. I will be updating this document as I actually learn more philosophy so follow this repo to see it evolve.

There is likely a strong Marxian justification for the prescription of the core principles, however, I've never read Marx and my understanding of socialism and communism is limited to whatever crumbs I've gained from watching thousands of hours of leftist streamers. Because of this limitation, we will use a far more naive, fundamental argument to arrive at our prescription: the purity of information exchange. While the purity argument certainly leaves more to be desired, note that this document is focused more on the descriptive anyway, so the prescriptive argument can be enhanced (and will eventually be) without effecting much of what is discussed.


## history of the "streamer website"

The streamer website following the corporate decoupling principle is not a new idea. The streamer [Destiny](destiny.gg) started their streamer website in [2013](https://github.com/destinygg/website/commit/0fcd5fbe5adfdab1e1392bb79924c09760eac5a4) and only [recently (late 2021)](https://github.com/destinygg/website/commit/4f4077671080bb9449435a8bb29f4379eb19a605) stopped publicly maintaining the repository (we discuss the implications of open source within the context of the streamer website in depth [later on](#open-source)). Sometime in 2018-2019(?), Destiny's open source streamer website was forked by [WhiteNervosa](https://github.com/WhiteNervosa) to service another streamer, [Vaush](vaush.gg); this fork ultimately culminated in another (and potentially the first) streamer website as a service, [WhiteLe.af](WhiteLe.af), whose goal is to ["provide a free and open source accessible platform for content creators"](WhiteLe.af). WhiteLe.af now powers the streamer websites of multiple streamers (~20) and is the primary model for streamforthepeople, which covers WhiteLe.af's features but does so in a way that is **massively scalable and easy to manage/modify**, making it the ideal service for fulfilling the **ownership transfer priniciple**.

## arriving at the core principles

For the purposes of this document, we'll simply define "streaming" as follows.
```
the live, online presentation of a continuous stream of data (usually both audio and video) by some individual or organization
```

The relationship between a streamer and their audience is one of information exchange; in its most basic form, this is a one-way exchange, the streamer "sending" their stream to their audience, however, we will be analyzing a slightly more complex exchange, one in which, additionally, the streamer's audience compensates the streamer for streaming. For now, let us assume that the parties in this exchange have fully consented to the exchange (we will discuss how consent is achieved by accessing streams through [aggregators](#aggregators)), then ideally, this exchange should be pure; that is, the information should flow **unchanged** from streamer to their audience and vice versa.

As a base case to demonstrate why such purity is one that ought to be achieved, consider a consensual conversation between individuals. In this case, the information being exchanged is simply the content and form of the words that each individual is "transmitting" (e.g. vocally, via text, via sign language, etc.) to the other. Embedded in the agreed-to "conversation" is the mutual understanding that due to the practical limitations of reality, the information being transmitted must pass through some abstract "gates" for the exchange to be realized, for the information to be received by the other. Then, the purity of the information exchange is some measure inversely proportional to aggregate effect the gates have on the information being exchanged. So to maximize the purity of information exchange, the transformations made on the information should be limited to those that enable the exchange to be realized, any transformation beyond this is categorically excessive, not because there may not exist some transformations that "improve" the exchange, but because any transformation made by such gates on the information is necessarily either detrimental to the purity of the information or external to its purity. In the case of the conversation between individuals, the gates depend entirely on the "platform" through which the individuals converse. Let's explore a handful of platforms and analyze how they effect purity. First, consider a telepathic convervation; to simplify this example, let's simply define the mechanism of the telepathy as precisely that which enables "gateless" information exchange between individuals. Because there does not exist gates through which the information must pass before the reaching the other individual, this exchange must be pure. Next consider a face to face conversation irl where each individual can speak perfectly, hear perfectly, and understand each other's language perfectly. In this case, the important gates introduced are the air through which the sound moves from the mouth of the speaker and the ear of the listener. Since the individuals' hearing is perfect, the only gate that can affect the purity of the exchange is the air between the conversators. Consider air conditions such that the sound output by the mouth of one remains unchanged as it moves through the air toward the ears of the other, then the exchange is pure . Now consider the case that these same individuals are having a conversation on [BART](https://www.sfgate.com/bayarea/article/BART-noise-levels-decibels-trains-headphones-loud-13602734.php); due to the other noise moving through the air, the delta caused by the air gate causes the exchange to be less pure. Finally, we must consider if the purity achievable by both platforms is the same. In both cases, the information is unchanged from source to sink, however the latter platform has more gates than the former, and is thus less pure, as purity is sensitive to minimalism. Although abstract gates don't seem to have any weight in existence, due to the way information is exchanged in reality (the existence of the gate has some non zero weight, e.g. the cost of maintaining the gate, the physical space that the gate occupies), we can trivially conclude that adding "identity" gates to exchanges that have already achieved purity is excessive. (maybe add cases of hearing aid and robo translator)

In order to understand how to maximize the purity of information exchange in the context of streaming, let's establish the stakeholders in the exchange.

- **streamer**: the individual or organization that produces the stream
- **audience**: the consumers of the stream
- (audio/video) **stream service provider**: the organization maintaining the servers that forward the bytes encoding the stream from the streamer to each member of their audience
- **streamforthepeople**: a streamer website as a service, consisting of a collection of services which suffice to fulfill the [core principles](#core-principles)

There is another "abstract" stakeholder, the **aggregator** which maintains an index/directory of streamers and can provide features like categorization, ranking, and recommendations; however, the aggregator is not essential to this exchange as it exists on higher level than the producer, consumer, and facilitators of the stream (they are a meta-stakeholder?). To prove this, consider that this exchange can exist without an aggregator. We will explore how the aggregator can trivially coexist with the other stakeholders both pre and post the ownership transfer period.

Because the stream service provider and streamforthepeople simply facilitate the exchange of bytes from the streamer to their audience, they are categorically different from the streamer and their audience, who actually embody the endpoints of the exchange. However, the stream service provider *is* necessary for the exchange to manifest as the stream could not be forwarded to the audience without the stream service provider. Critically consider that the necessity of the stream service provider is tied to the limitations of reality; that is, the stream could not be forwarded from the streamer to their audience without the stream service provider, because there does not exist an alternative gateway to achieve the same information transfer. For example, if the streamer were able to telepathically project the stream directly into the minds of their audience, this would more purely achieve the exact same exchange, as it is done without the stream service provider, (at least) 1 fewer gate. Thus, we should aim to "minimize" the stream service provider in the exchange, as their presence in the exchange is simply an incidental consequence of their providing a gateway which fulfills the requirements of enabling the desired information exchange within the bounds of current technology.

So then the question is: how do we "minimize" the stream service provider in this exchange? The metrics I propose to measure are of agnosticity of stream service provider and revenue cut that the stream service provider negotiates with the streamer. An extra metric is the feature set provided to the audience, but this should be strictly secondary to maximizing agnosticity and minimizing the revenue cut. I assert that fulfilling the core principles will accomplish this.

TODO:
- understanding coupling
- why decoupling will increase purity
- what is ownership in this context
- who ought to own
- how can this be achieved
- the way i will assist in achieving it

### y go it alone

i am avi ur philosopher king architect engineer and i will be guiding streamforthepeople in it's transitionary period to fulfilling the core principles, henceforth, the pre ownership transfer period

u r prolly wondering y i would go it alone, 1: it's my baby, 1: to enrich myself, 1: because the scope of the requirements are extremely (relatively) limited + modern tooling empowers the individual to effectively manage massively scalable automated systems, 1: i won't not go it alone (get fucked, die mad), 1: pros/cons of multiple ppl; pros: features get developed faster, more adhoc support, support backlog gets processed faster, >1 minds are greater than 1?, no single point of failure; cons: non unified vision, actually acquiring someone who would aspire to fulfilling the ownership transfer principle, i make less money, management of profit spread/work inequality, individuals may not be generalist, many potential angries

## open source

## aggregators

### notes/to delete

Unravelling the essence of the streamer website which fulfills the corporate decoupling principle will allow us to understand why fulfilling the core principles is the ideal way to maximize the quality of exchange between streamers and their audience. understand why the requirements are actually relatively simple abstractions, and that the power is unjustly and unnecessarily pooled in the places which make the least sense in the context of the exchange

so first we need to understand y the streamer's audience is coupled to the stream service provider. it is the combination of 3 things: the stream service provider hosts the stream + the stream service provider also operates as an aggregator, which ppl feel nationalistic about + features provided by the stream service provider

being an aggregator is easy, the streamer website can handle the other stuff. the streamer website can host the stream, i.e. host as in embed the output of the stream service provider, and streamer website can provide a feature set that matches and exceeds that of the stream service provider because the features will not have the goal of maximizing the revenue generated for the stream service provider, sometimes only incidentally actually providing value for the audience

The live-ness, online-ness, and continuity of the stream of data is embedded into the stream itself. In fact, these properties are simply sufficient components for the actually important emergent property of audience synchronicity in the consumption of some content. but the synchronicity isn't enuf cuz like u get it in a movie theater or a college lecture, but clearly there's something different, so let's pick apart these examples and attempt to achieve parity with what a stream provides, is it even possible?
what synchronizes the audience is some combination of the chat and the content being presented, since the chat doesn't synchronize itself in content, only in time and place, as everyone in stream could be watching any content and chatting about anything, and the content doesn't synchronize the chat because not all content compels the chats to synchronize

Because streams are able to reach massive audiences, streamers primarily interact with their audience through a chat. As the streamer presents, the chat provides their audience the ability to react to and communicate with the streamer in real time. The chat is the primary element of the streamer website and is essential to fulfilling the corporate decoupling principle.
