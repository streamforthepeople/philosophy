# the philosophy of streamforthepeople

[**streamforthepeople**](https://streamforthepeople.com) is a **streamer website as a service**

This document discusses its philosophy. **TLDR**: see the [core principles](#core-principles)

## **core principles**

1. To decouple the streamer's audience from the stream service provider; henceforth, the **corporate decoupling principle**.
1. To transfer ownership of this service to the streamers, where it would be operated, managed, and governed by some democratic body of streamers, e.g. a "streamer's guild"; henceforth, the **ownership transfer principle**.

## disclaimers
While I did take a philosophy class in college (it was about data philosophy heh), I am only an amateur philosopher. As such, this document will likely lack some rigor and not fill in all the expected philosophical gaps; if you find anything of concern and would like to address it, please create an issue or pull request on this repo and we can discuss it. I will be updating this document as I actually learn more philosophy so follow this repo to see it evolve.

There is likely a strong Marxist justification for the prescription of the core principles, however, I've never read Marx and my understanding of socialism and communism is limited to whatever crumbs I've gained from watching thousands of hours of leftist streamers. Because of this limitation, we will use a far more naive argument to arrive at our prescription: the control of purity of information exchange. While (imo) this purity argument leaves more to be desired, note that this document is focused more on the descriptive anyway, so the prescriptive argument can be enhanced (and eventually will be) without effecting much of what is discussed.


## history of the "streamer website"

The streamer website which fulfills the **corporate decoupling principle** is not a new idea. The streamer [Destiny](destiny.gg) started their streamer website in [2013](https://github.com/destinygg/website/commit/0fcd5fbe5adfdab1e1392bb79924c09760eac5a4) and only [recently (late 2021)](https://github.com/destinygg/website/commit/4f4077671080bb9449435a8bb29f4379eb19a605) stopped publicly maintaining the repository (we discuss the implications of open source within the context of the streamer website in depth [later on](#open-source)). [In early 2019](https://github.com/ILiedAboutCake/blog/blob/master/content/posts/04-22-2021-a-timeline-of-destinygg-website-and-forks.md#vaush-and-whiteleaf-sites), Destiny's open source streamer website was forked by [WhiteNervosa](https://github.com/WhiteNervosa) to service another streamer, [Vaush](vaush.gg); this fork ultimately culminated in another (and likely the first) streamer website as a service, [WhiteLe.af](WhiteLe.af), whose goal is to ["provide a free and open source accessible platform for content creators"](WhiteLe.af) (however, note that it is not currently open source). WhiteLe.af now powers the streamer websites of multiple streamers (~20) and is the primary model for **streamforthepeople**, which covers many of WhiteLe.af's features, adds more, and does so in a way that is **massively scalable and easy to manage/modify** ([cloud native](https://en.wikipedia.org/wiki/Cloud_native_computing), [kubernetes](https://kubernetes.io/) orchestrated, [asynchronous](https://en.wikipedia.org/wiki/Asynchrony_(computer_programming)) [microservices](https://en.wikipedia.org/wiki/Microservices) with [CI/CD](https://en.wikipedia.org/wiki/CI/CD), ergonomically written in [**Python**](https://www.python.org/) + [**Rust**](https://www.rust-lang.org/)), making it the ideal service for fulfilling the **ownership transfer priniciple**.

## arriving at the core principles

For the purposes of this document, we'll simply define "streaming" as follows.
```
the live, online presentation of a continuous stream of data (usually both audio and video) by some individual or organization
```

The relationship between a streamer and their audience is one of information exchange; in its most basic form, this is a one-way exchange, the streamer "sending" their stream to their audience, however, we will be analyzing a slightly more complex exchange, one in which, additionally, the streamer's audience compensates the streamer for streaming. For now, let's assume that the parties in this exchange have fully consented to the exchange (we will discuss how consent is achieved by accessing streams through [aggregators](#aggregators)); then, **the aggregate influence of the streamer and their audience on the purity of information exchange ought be maximized**.

### understanding purity of information exchange (POIE)
**what is it?** As a base case to demonstrate what this purity is, consider a consensual (TODO: consent feels like it's carrying some weight here, but that weight is not relevant here, need to explain why this assumption is reasonable) conversation between individuals. In this case, the information being exchanged is simply the content and form of the words (information) that each individual is "transmitting" (e.g. vocally, via text, via sign language, etc.) to the other. Embedded in the agreed-to "conversation" is the mutual understanding that due to the practical limitations of reality, the information being transmitted must pass through some abstract "gates" for the exchange to be realized (i.e. for the information to travel from one endpoint to the other); these gates "touch" the information, <u>potentially</u> applying various transformations to the information which <u>may</u> enable the information to be received by the other individual. Then, the POIE is some measure inversely proportional to the aggregate effect the gates have on the information being exchanged; this aggregate effect is some function of each gate's touch. (Note: information *passing through* a gate is equivalent to a gate *touching* information, each is used when convenient)

Before exploring why we might want to minimize the effects of these gates and whether POIE is desirable in general, let's first illustrate what different levels of purity look like in our base case. To maximize the POIE, the transformations made on the information should be limited to those that enable the exchange to be realized; any transformation beyond this is <u>categorically excessive</u>. Critically, although there may exist some transformations that "improve" the exchange (see the robo translator example below), any such transformation is necessarily either detrimental to the POIE or external to its POIE. In the case of the conversation between individuals, the gates depend entirely on the "platform" through which the individuals converse. Let's explore a handful of platforms and analyze how they affect purity.

First, consider a telepathic convervation. To simplify this example, let's define the mechanism of the telepathy as precisely that which enables "gateless" information exchange between individuals. Because there does not exist gates through which the information must pass before the reaching the other individual, the platform's POIE is maximized. Next, consider a face to face conversation [irl](https://www.urbandictionary.com/define.php?term=irl) where each individual can speak perfectly, hear perfectly, and understand each other's language perfectly. In this case, the important gates introduced are the air through which the sound moves from the mouth of the speaker, and the ear of the corresponding listener. Since each individual's hearing is perfect, the only gate that can affect the purity of information exchange is the air between the conversators. Consider air conditions such that the sound output by the mouth of one remains unchanged as it moves through the air toward the ears of the other; that is, precisely the conditions such that the "air gate" functions as an [identity](https://en.wikipedia.org/wiki/Identity_function) gate, one that touches the information (or one that the information *passes through*) but *does not* transform it in any way. Then, the platform's POIE is maximized. Now consider the case that these same individuals are having a conversation on [BART](https://www.sfgate.com/bayarea/article/BART-noise-levels-decibels-trains-headphones-loud-13602734.php); due to the other noise moving through the air, the transformation applied to the information by the air gate can, at worst, restrict the information exchange entirely and will, at the very least, significantly change the information as it reaches the listener, decreasing the POIE.

Next, let's consider the differences between the maximum purity achievable by both platforms. In both cases, the information is unchanged from source to sink, however, the latter platform has more gates than the former, and is thus less pure. Why is this? If the information was received as it was transmitted, how can the POIE be lower? To understand this, let's revisit the identity air gate from above. While this hypothetical gate does not *change* the information as it passes through the gate, the gate still *does something* to the information, enable it to flow from the mouth of one individual to the ears of the other. If we drop the air gate, then the exchange can no longer be realized. This contrasts with the telepathic platform, which realizes the exchange entirely without gates. Now imagine we had the ability to "append" additional identity air gates to the existing one, something like the below, where `IAG = identity air gate`
```
individual 1 <-> IAG 1 <-> IAG 2 <-> ... <-> IAG N-1 <-> IAG N <-> individual 2
```
such that as long as there remains at least 1 air gate between the individuals, the exchange is still realized. Recall that each identity air gate has no effect on the information that passes through it, other than "the passing" itself; embedded in the passing is an underlying *mechanism* with which the gate interacts with the information in any way (i.e. the means by which the gate touches the information/enables it to pass through the gate). If POIE were agnostic to each gate's mechanism, then the POIE is the same for all N in the example above, however POIE is sensitive to mechanistic side effects *even if* the mechanism is perfectly understood. This is conservative because, for example, the identity air gate may be understood to have no mechanistic side effects, bringing its effective POIE to parity with the telepathic platform; however this conservatism is not arbitrarily introduced to distinguish between the maximum POIE achievable both telepathically and irl, it is simply a reasonable bias to have due to the weight that gates have in reality. This weight can take various forms, like the cost of maintaining the gate, the physical space the gate occupies, some meta-mechanism etc., and can be holistically understood as the *management* of the mechanism. For example, although we understand the physical mechanism that enables [sounds to pass through air](https://en.wikipedia.org/wiki/Sound#Physics), we do not (yet?) understand the underlying metaphysical management of this behavior. In this layer (potentially) lies the side effects that we are conservative towards the existence of. Thus, although each identity air gate does not change the information as it passes through the gate, each one potentially has mechanistic side effects whose influence we hedge against with a more conservative understanding of POIE. And therefore, the maximum POIE achievable by the irl platform is lower than that of the telepathic platform and would decrease with each additional identity air gate.

**is POIE good in general?** no, but the influence on it by the endpoints of the exchange ought be maximized (why? ostensibly, the endpoints of the exchange should be able to negotiate POIE modifiers that best improve the exchange, electing to utilize third parties as desired, like perhaps to address influence inequality between each endpoint; in the case of the streamers guild, they will have more influence than viewers, but this is ok ...) ... (TODO)
TODO: speaking perfectly and hearing perfectly are not actually relevant, the only thing that is relevant is that the information is received as transmitted, which should be made clear in robo translator (gate which improves an interlanguage conversation, decreases POIE) vs hearing aid (gate which improves conversation, increases POIE) examples

If the above abstractions did not make sense (sorry they'll get better lol), below, we solidify them within the context of the streamer website. For example, the stream service provider gate's mechanism is the runtime of the stream forwarding server, and its management is the operation of that runtime by some corporation, which has *many* side effects due to the cost of this operation and the corporations motives, some known, some unknown, but all undeniably reducing the POIE of the exchange entirely outside the influence of the streamers and their audience.

---

In order to understand how to maximize the POIE in the context of streaming, let's establish the stakeholders in the exchange.

- **streamer**: the individual or organization that produces the stream
- **audience**: the consumers of the stream
- (audio/video) **stream service provider**: the organization maintaining the servers that forward the bytes encoding the stream from the streamer to each member of their audience
- **streamforthepeople**: a streamer website as a service, consisting of a collection of services which suffice to fulfill the [core principles](#core-principles)

There is another "abstract" stakeholder, the **aggregator** which maintains an index/directory of streamers and can provide features like categorization, ranking, and recommendations; however, the aggregator is not essential to this exchange as it exists on higher level than the producer, consumer, and facilitators of the stream (they are a meta-stakeholder?). To prove this, consider that this exchange can exist without an aggregator. We will explore how the aggregator can trivially coexist with the other stakeholders both pre and post the ownership transfer period.

Because the stream service provider and streamforthepeople simply facilitate the exchange of bytes from the streamer to their audience, they are categorically different from the streamer and their audience, who actually embody the endpoints of the exchange. However, the stream service provider *is* necessary for the exchange to manifest as the stream could not be forwarded to the audience without the stream service provider. Critically consider that the necessity of the stream service provider is tied to the limitations of reality; that is, the stream could not be forwarded from the streamer to their audience without the stream service provider, because there does not exist an alternative gate to achieve the same information transfer. For example, if the streamer were able to telepathically project the stream directly into the minds of their audience, this would more purely achieve the exact same exchange, as it is done without the stream service provider, (at least) 1 fewer gate. Thus, we should aim to "minimize" the stream service provider (TODO: need to make clear that minimization is also specifically targetting the opaque side effects that the relationship with a corporate stream service provider introduces) in the exchange, as their presence in the exchange is simply an incidental consequence of their providing a gateway which fulfills the requirements of enabling the desired information exchange within the bounds of current technology.

So then the question is: how do we "minimize" the stream service provider in this exchange? The metrics I propose to measure are of agnosticity of stream service provider and revenue cut that the stream service provider negotiates with the streamer. An extra metric is the feature set provided to the audience, but this should be strictly secondary to maximizing agnosticity and minimizing the revenue cut. I assert that fulfilling the core principles will accomplish this.

TODO:
- understanding coupling
- why decoupling will increase purity
- what is ownership in this context
- who ought to own
- how can this be achieved
- the way i will assist in achieving it

### y go it alone

i am avi ur philosopher king architect engineer and i will be \~softly\~ guiding streamforthepeople in it's transitionary period to fulfilling the core principles, henceforth, the pre ownership transfer period

ur prolly wondering y i would go it alone
1. it's my baby (and i can do whatever i want w my baby because i brought it into this world)
1. to enrich myself ($$$)
1. because the scope of the requirements are extremely (relatively) limited + modern tooling empowers the individual to effectively manage massively scalable automated systems
1. i won't not go it alone (get fucked, die mad)
1. pros/cons of multiple ppl
    - pros:
        - features get developed faster
        - more adhoc support
        - support backlog gets processed faster
        - \>1 minds are greater than 1?
        - no single point of failure (resiliency to me dying, prolly getting murdered by the stream service providers)
    - cons:
        - non unified vision
        - acquiring someone who would actually aspire to fulfilling the ownership transfer principle
        - i make less money (cringe)
        - management of profit spread/work inequality
        - individuals may not be generalist
        - many potential angries

## streamforthepeople's cut
In the pre ownership transfer period, streamforthepeople will take 15% of subscriptions and 5% of donations. My justification for the 15% is that Patreon simply functions as a consolidated subscription platform with an aggregator and [takes 5%](https://www.patreon.com/pricing), so since streamforthepeople does this and also streamer website features it certainly warrants more. How I got to 15% specifically is because I would feel uncomfortable taking a percentage with a 2 as the first number because 2 is twice as big as 1 and therefore seems excessive; the first number being a 1 feels a lot more reasonable. So I think the number in the middle of 10 and 20 is a nice compromise. For the 5% of donations, this is just parity with patreon. Note that in the post ownership transfer period, the streamer's guild will democratically decide its member's dues, which will certainly be less than cuts above.

## open source (TODO)
We want to understand what open source is good for and in what contexts it's efficacious, we can also look at the current streamer website offerings (specifically [dgg](https://github.com/destinygg/website) and its [history](https://github.com/ILiedAboutCake/blog/blob/master/content/posts/04-22-2021-a-timeline-of-destinygg-website-and-forks.md)) and analyze if the open source-ness actually had the intended effect, one that streamforthepeople will *actually* have, specifically, offering a service fulfilling the **corporate decoupling principle** to **as many streamers as possible**, and offering a pathway to a more reasonable model of ownership via a streamer's guild with the **ownership transfer principle**.

## aggregators (TODO)

### notes/to delete

Unravelling the essence of the streamer website which fulfills the corporate decoupling principle will allow us to understand why fulfilling the core principles is the ideal way to maximize the quality of exchange between streamers and their audience. understand why the requirements are actually relatively simple abstractions, and that the power is unjustly and unnecessarily pooled in the places which make the least sense in the context of the exchange

so first we need to understand y the streamer's audience is coupled to the stream service provider. it is the combination of 3 things: the stream service provider hosts the stream + the stream service provider also operates as an aggregator, which ppl feel jingoistic about + features provided by the stream service provider

being an aggregator is easy, the streamer website can handle the other stuff. the streamer website can host the stream, i.e. host as in embed the output of the stream service provider, and streamer website can provide a feature set that matches and exceeds that of the stream service provider because the features will not have the goal of maximizing the revenue generated for the stream service provider, which usually only incidentally actually provides value for the audience

The live-ness, online-ness, and continuity of the stream of data is embedded into the stream itself. In fact, these properties are simply sufficient components for the actually important emergent property of audience synchronicity in the consumption of some content. but the synchronicity isn't enuf cuz like u get it in a movie theater or a college lecture, but clearly there's something different, so let's pick apart these examples and attempt to achieve parity with what a stream provides, is it even possible?
what synchronizes the audience is some combination of the chat, the content being presented, and the streamer, since the chat doesn't synchronize itself in content, only in time and place, as everyone in stream could be watching any content and chatting about anything, the content doesn't synchronize the chat because not all content compels the chats to synchronize, and the streamer can only measure synchronicity relative to the chat's behavior

Because streams are able to reach massive audiences, streamers primarily interact with their audience through a chat. As the streamer presents, the chat provides their audience the ability to react to and communicate with the streamer in real time. The chat is the primary element of the streamer website and is essential to fulfilling the corporate decoupling principle.
