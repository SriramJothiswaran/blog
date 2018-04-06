---
layout: post
current: post
cover: /assets/images/blockchain-and-the-supply-chain.png
navigation: true
title: 5 Questions why you should Blockchain Technology
date: '2018-04-06T23:27:24+05:30'
tags: blockchain
class: post-template
subclass: tag blockchain
author: sriram
published: false
---
As the market around blockchain continues to grow, a range of different distributed ledger technologies are becoming available for enterprise users to apply blockchain. When looking at your options, it is important to note that certain protocols are suited to certain use cases, and time-to-value can be accelerated by leveraging existing networks that already exist. In this blog, I will give you a series of questions to consider when selecting a distributed ledger technology.



**Is the protocol open sourced and openly governed?**

Simply posting code on an open developer site is not enough — there needs to be a governing body which maintains the code in line with enterprise needs.Hyperledger openly validates the inputs through the Technical Steering Committee to ensure innovations are supported which harden blockchain for business.

The recent addition of zero-knowledge proofs and identity mixer to Hyperledger Fabric demonstrates Hyperledger’s willingness to support continuous innovation for enterprise needs.

Other protocols such as Ethereum and Corda lie at the hands of a very small group of developers, often from a single organization. This means they centrally control the roadmap of their technologies, ultimately at the expense of innovation in the long run.



**Who will be a part of the network?**

The next key question for an organization is; who are the intended participants of the blockchain network? Participants can include business partners, application providers, regulators or even competitors.

The majority of enterprise networks require that at least a core subset of the network members, if not all, need to be known to each other. We call this a permission network. Hyperledger Fabric allows a common identity verification scheme to be configured for a network. This scheme can be configured for a small private network, or for a more distributed public facing network. The key consideration is whether sufficient data will be known so that you can interact with a sufficient trust in who is on the other side.

Many other enterprise protocols rely on single organizations to act as gates to approve participants as well as transactions. This model struggles to scale as the network grows.



**What use case will drive transactions on the network?**

Another key consideration when choosing a protocol is the types of transactions that will be submitted to the network.

If the transactions are for an arbitrary asset type — as in defined for the network and representing a physical or digital asset — a programming model like Hyperledger Composer can be used to model the assets, participants and transactions. This can then be deployed to a running instance of Hyperledger Fabric.

This is also when you should consider the privacy and security implications of your transactions. In many cases you may need a protocol that will allow you to keep transaction data private between participants.

The use case may also necessitate the use of a trusted public network when dictated by a business need. Two prime examples of this are for trusted identity and universal payments. For instance, a distributed ledger like Stellar enables transfer of cross-border payments, enabling universal settlement of assets.



**Is the technology modular and easy to use?**

Perhaps one of the most critical aspects of a distributed ledger technology for enterprise use is the ability to configure the technology for an enterprise use-case.

Key features such as consensus, permissions and database, should be modular to the needs of a specific use case. For instance, one use-case may require every participant in the network to endorse transactions before they are considered valid, while others may have less stringent requirements.

Many distributed ledger technologies struggle to support needed levels of modularity and therefore have to rely on bulky consensus protocols like proof of work in order to scale. Even worse, making changes to these aspects of the network even when used for a private network may require complex development processes to adapt.

Corda, for instance, is only configurable for private networks in the financial space, rather than being a modular technology which can be used for a range of use cases across industries, integrating multiple additional technologies for IoT.

**How does blockchain meet the other key enterprise requirements?**

* **Scalability** – Distributed ledger technologies must be able to scale as the network grows in terms of both transactions and participants. Things such as centralized validation services and complex peer compiling processes have a high likelihood of limiting scale.
* **Regulatory risk **– One of the biggest open questions in the blockchain space is the regulatory perspective on cryptocurrencies as an application of distributed ledger technology. Due consideration should be given to the likelihood of regulatory action on protocols supporting public cryptocurrencies.
* **Skills availability** – The blockchain space has seen a number of high profile data and asset breaches due to the immaturity of new programming languages. Enterprise users should leverage distributed ledger technologies which enable their developers to work with tools and programming languages they are already familiar with.
* **Support **– Like any enterprise application, there needs to be an appropriate level of support for the entire stack. Whether through open source communities or platform and solution providers, support is needed from the build to production phases of adoption.
