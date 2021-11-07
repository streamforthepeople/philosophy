# the philosophy of streamforthepeople

**streamforthepeople** is a **streamer website as a service**

This document discusses its philosophy. **TLDR**: see the [core principles](#core-principles)

## core principles

1. to decouple the streamer's audience from the stream service provider; henceforth, the **corporate decoupling principle**
1. to transfer ownership of this service to the streamers, where it would be operated, managed, and governed by some democratic body of streamers, e.g. a "streamer's guild"; henceforth, the **ownership transfer principle**

## analysis of core principles

### history of the "streamer website"

The streamer website following the corporate decouple principle is not a new idea. The streamer [Destiny](destiny.gg) started their streamer website in [2013](https://github.com/destinygg/website/commit/0fcd5fbe5adfdab1e1392bb79924c09760eac5a4) and only [recently (late 2021)](https://github.com/destinygg/website/commit/4f4077671080bb9449435a8bb29f4379eb19a605) stopped publicly maintaining the repository (we discuss the implications of open source within the stream website context in depth [later on](#open-source)). Sometime in 2018-2019(?), Destiny's open source streamer website was forked by [WhiteNervosa](https://github.com/WhiteNervosa) to service another streamer, [Vaush](vaush.gg); this fork ultimately culminated in another (and potentially the first) streamer website as a service, [WhiteLe.af](WhiteLe.af), whose goal is to ["provide an free and open source accessible platform for content creators"](WhiteLe.af). WhiteLe.af now powers the streamer websites of multiple streamers (~10?) and is the primary model for streamforthepeople, which covers WhiteLe.af's features but does so in a way that is **massively scalable and easy to manage/modify**.

### anatomy of the streamer website

For the purposes of this document, we'll simply define "streaming" as follows.
```
the live, online presentation of a continuous stream of data (usually both audio and video) by some individual or organization
```

outline:
discuss the ideal purity of the information exchange and why this purity is good
discuss y the necessity of the ssp is one of incidence, they r simply the owners of the machines that can best facilitate the exchange given current technological limitations
discuss y audience is currently coupled w the ssp
discuss strategies to decouple

The relationship between a streamer and their audience is fundamentally one of information exchange. Ideally, this exchange of information should be pure, that is, the information should flow unfettered from streamer to audience and vice versa with very little noise in between, and the audience should be able to compensate the streamer with minimal skimming from middle-NBs. Unravelling the essence of the streamer website which fulfills the corporate decoupling principle will allow us to understand why fulfilling the core principles is the ideal way to maximize the quality of exchange between streamers and their audience. understand why the requirements are actually relatively simple abstractions, and that the power is unjustly and unnecessarily pooled in the places which make the least sense in the context of the exchange

First, let us establish the stakeholders in this exchange.

- **streamer**: the individual or organization that produces the stream
- **audience**: the consumers of the stream
- (audio/video) **stream service provider**: the organization maintaining the servers that forward, and critically, replicate, the bytes encoding the stream from the streamer to each member of their audience
- **streamforthepeople**: a streamer website as a service, consisting of a collection of services which suffice to fulfill the [core principles](#core-principles)

There is another "abstract" stakeholder, the **aggregator** which maintains an index/directory of streamers and can provide features like categorization, ranking, and recommendations; however, the aggregator is not essential to this exchange as it exists on higher level than the producer, consumer, and facilitators of the stream. To prove this, consider that this exchange can exist without an aggregator. We will explore how the aggregator can trivially coexist with the other stakeholders both pre and post the ownership transfer period.

Because the stream service provider and streamforthepeople simply facilitate the exchange of bytes from the streamer to their audience, they are categorically different from the streamer and their audience, who actually embody the producer and consumer of the exchange. However, the stream service provider *is* necessary for the exchange to manifest as the stream could not be forwarded to the audience without the stream service provider. Consider that the necessity of the stream service provider is tied to the limitations of reality, that is, the stream could not be forwarded from the streamer to their audience without them, because there does not exist an alternative to achieve the same information transfer. For example, if the streamer were able to project the stream directly into the minds of their audience, this would more purely achieve the exact same exchange, as it is done without the stream service provider. Thus, we should aim to "minimize" the stream service provider in the exchange, since their presence in the exchange is simply an incidental consequence of the fulfilling the requirements to enable the desired information exchange within the bounds of current technology.

So then the question is: how do we "minimize" the stream service provider in this exchange? The metrics i propose to measure are of agnosticity of stream service provider and revenue cut that the stream service provider negotiates with the streamer. an extra metric is the feature set provided to the audience, but this is for later. so minimization of the stream service provider would be accomplished by maximizing the agnosticity to the stream service provider that they use, while also minimizing the revenue cut taken by the stream service provider. i assert that fulfilling the core principles will accomplish this minimization. 

so first we need to understand y the streamer's audience is coupled to the stream service provider. it is the combination of 3 things: the stream service provider hosts the stream + the stream service provider also operates as an aggregator, which ppl feel nationalistic about + features provided by the stream service provider

being an aggregator is easy, the streamer website can handle the other stuff. the streamer website can host the stream, i.e. host as in embed the output of the stream service provider, and streamer website can provide a feature set that matches and exceeds that of the stream service provider because the features will not have the goal of maximizing the revenue generated for the stream service provider, sometimes only incidentally actually providing value for the audience

The live-ness, online-ness, and continuity of the stream of data is embedded into the stream itself. In fact, these properties are simply sufficient components for the actually important emergent property of audience synchronicity in the consumption of some content. but the synchronicity isn't enuf cuz like u get it in a movie theater or a college lecture, but clearly there's something different, so let's pick apart these examples and attempt to achieve parity with what a stream provides, is it even possible?
what synchronizes the audience is some combination of the chat and the content being presented, since the chat doesn't synchronize itself in content, only in time and place, as everyone in stream could be watching any content and chatting about anything, and the content doesn't synchronize the chat because not all content compels the chats to synchronize

Because streams are able to reach massive audiences, streamers primarily interact with their audience through a chat. As the streamer presents, the chat provides their audience the ability to react to and communicate with the streamer in real time. The chat is the primary element of the streamer website and is essential to fulfilling the corporate decoupling principle.


### y go it alone

i am avi ur philosopher king architect engineer and i will be guiding streamforthepeople in it's transitionary period to fulfilling the core principles, henceforth, the pre ownership transfer period

u r prolly wondering y i would go it alone, 1: it's my baby, 1: to enrich myself, 1: because the scope of the requirements are extremely limited + modern tooling empowers the individual to effectively manage massive automated systems, 1: i won't not go it alone, 1: pros/cons of multiple ppl; pros: features get developed faster, more adhoc support, support backlog gets processed faster, >1 minds is greater than 1?, no single point of failure; cons: non unified vision, actually acquiring someone who would aspire to fulfilling the ownership transfer principle, i make less money, management of profit spread/work inequality, individuals may not be generalist, many angries


### open source