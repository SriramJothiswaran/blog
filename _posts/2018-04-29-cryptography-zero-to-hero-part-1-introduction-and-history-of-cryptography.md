---
layout: post
current: post
cover: assets/images/crypto.png
navigation: true
title: Cryptography zero to hero - part 1| Introduction and history of Cryptography
date: '2018-04-29T15:05:08+05:30'
tags: cryptography
class: post-template
subclass: tag-cryptography
author: sriram
published: true
---
# Cryptography zero to hero - part 1| Introduction and history of Cryptography

In my previous posts you can see more about blockchain, i thought of introducing you to understand how blockchain works and move towards blockchain frameworks like hyperledger and Ethereum Dapps. If you have read my previous articles **Understand Blockchain - Beginner to Advanced -** [**Part 1**](https://blog.sriramj.xyz/understand-blockchain-beginner-to-advanced) **&** [**Part 2**](https://blog.sriramj.xyz/understand-blockchain-beginner-to-advanced-part-2) ****you would have got some theoretical overview of how blockchain works. Lets get more deeper and understand blockchain at a very ground level. Be it public or private blockchain everyone needs the data to be safe and secure, cryptography is the art of securing information. This article will provide details why and where cryptography is being used and some historical cryptographic techniques.


**Objectives:-**

1. Learn how crypto primitives work
2. Learn how to use them correctly and reason about security
3. What is Cryptography ?
4. History of Cryptography ?

**Cryptography is everywhere**

Cryptography is everywhere computers are, its a very common tool to protect data.
For example:

- Web traffic is protected using protocol HTTPS
- Wireless traffic is protected using WPA2(802.11i), GSM, Bluetooth
- Files on disk are encrypted using protocols EFS, TrueCrypt
- Content protecting in DVD’s and Bluray using protocols Content Scrambling System (CSS) and AACS
- User Authentication and lot more

**Secure Communication**


![](https://d2mxuefqeaa7sj.cloudfront.net/s_B9864D4913735962AC3DE2BAA0D3BFE8B8192C1A5FD3A5D869FB844E4A174363_1524926580595_ssl-connection-t.jpg)


Now lets see how cryptography is used to secure communication. Refer above image, we have a server and a laptop which is the client. A lot of the internet has recently been switching to something called HTTPS protocol. This allows for all communications between the client and server to be encrypted through the use of public key encryption.

The protocol that is used to build this secure channel is HTTPS but the actual protocol is  SSL/TLS. The goals of this protocol is basically to make sure that data travels across the network an attacker cannot eavesdrop on this data. Secondly, the attacker cannot modify the data while it’s in the network. So, no eavesdropping, no tampering.

The non-secure HTTP (hyper-text transfer protocol) generally transmits all of it’s data in plaintext (though there are exceptions, such as when JavaScript is involved). This means that anyone that could intercept the message (such as on the same WiFi network) could plainly read the data being sent between the client’s machine and the server. This can include passwords, credit card data, and other sensitive information. For this reason, https was created.


Secure Socket Layer (SSL)/ TLS actually consists of two main parts :-   


![](https://d2mxuefqeaa7sj.cloudfront.net/s_B9864D4913735962AC3DE2BAA0D3BFE8B8192C1A5FD3A5D869FB844E4A174363_1524929007150_1.png)




   (i) Handshake protocol to establish shared secret key using public-key cryptography.See the above image, basically at the end of the handshake a shared secret key appears between two of the them. Both alice and bob knows the secret key but the attacker looking at the conversation has no idea what the key is. We can use this key to communicate securely by properly encrypting the data between them.

   (ii) Record layer to transmit data using shared secret key

will cover more about them in later articles.

**Protection of files on disk**

![](https://d2mxuefqeaa7sj.cloudfront.net/s_B9864D4913735962AC3DE2BAA0D3BFE8B8192C1A5FD3A5D869FB844E4A174363_1524975749847_file-protection-final.png)





Another application of cryptography is to protect files on disk. See above image, here we have file that happens to be encrypted. So, even if the disk is stolen an attacker can’t actually read the contents of the file. If an attacker tries to modify the data on disk, when alice tries to decrypt this file that will be detected and obviously alice will then ignore the content of tampered file. Here we have both integrity and confidentiality for files stored on disk. This is analogous to secure communication which we saw earlier. In particular, storing files on disk its alice who encrypts and decrypts the file. While on secure communication we had alice and bob involved in encryption & decryption processes.

The building block for securing traffic is called symmetric encryption.

**Symmetric Encryption**

Symmetric-key algorithms are algorithms for cryptography that use the same cryptographic keys for both encryption of plaintext and decryption of ciphertext. The keys may be identical or there may be a simple transformation to go between the two keys. The keys, in practice, represent a shared secret between two or more parties that can be used to maintain a private information link.

![](https://d2mxuefqeaa7sj.cloudfront.net/s_B9864D4913735962AC3DE2BAA0D3BFE8B8192C1A5FD3A5D869FB844E4A174363_1524980898476_symmetric-encryption.png)


Symmetric encryption system basically two parties alice & bob share secret key (k) which attacker doesn’t know. Only then know the secret key k, Now, they’re gonna use a cipher which consists of these two algorithms  E (encryption) and D (decryption). Encryption algorithm takes message & key as input and produces a corresponding ciphertext. And the decryption algorithm does the opposite, it takes ciphertext & key as input and produces the corresponding message.

 Now, a very important point that I would like to stress. I'm only gonna say this once now and never again, but it is an extremely important point. And that is: that the algorithms E and D, the actual encryption algorithms are publicly known. Adversary knows exactly how they work. The only thing that's kept secret is the secret key k. Other than that everything else is completely public and it's really important to realize that you should only use algorithms that are public because those algorithms have been peer-reviewed by a very large community of hundreds of people for many, many, many years, and these algorithms only begin to be used once this community has shown that they cannot be broken, essentially. So in fact, if somebody comes to you and says, hey, I have a proprietary cipher that you might want to use, the answer usually should be that you stick to standards, to standard algorithms, and not use a proprietary cipher. In fact, there are many examples of proprietary ciphers that, as soon as they were reverse engineered, they were easily broken by simple analysis.

 **Things to remember**

 Cryptography is

  1. the basis for many security mechanisms
  2. a tremendous tool


Cryptography is not

  1. the solution to all security problems
  2. reliable unless implemented and used properly
  3. something you should try to invent yourself
  
----------

Before we start with the technical material, I wanna give you a quick overview of what cryptography is about and the different areas of cryptography. So the core of cryptography of course is secure communication that essentially consists of two parts. The first is secured key establishment and then how do we communicate securely once we have a shared key. We already said that secured key establishment essentially amounts to Alice and Bob sending messages to one another such that at the end of this protocol, there's a shared key that they both agree on, shared key K, and beyond that, beyond just a shared key, in fact Alice would know that she's talking to Bob and Bob would know that he's talking to Alice. But a poor attacker who listens in on this conversation has no idea what the shared key is. Now once they have a shared key, they want to exchange messages securely using this key, and we'll talk about encryption schemes that allow them to do that in such a way that an attacker can't figure out what messages are being sent back and forth. And furthermore an attacker cannot even tamper with this traffic without being detected. In other words, these encryption schemes provide both confidentiality and integrity. But cryptography does much, much, much more than just these two things.

**Crypto can do much more**


- **Digital Signatures**

First example i want to give is called a digital signature. So, a digital signature is basically analog of signature in physical world.In the physical world, remember when you sign a document, essentially, you write your signature on that document and your signature is always the same. You always write the same signature on all documents that you wanna sign. In the digital world, this can't possibly work because if the attacker just obtained one signed document from me, he can cut and paste my signature into some other document that I might not have wanted to sign. And so, it's simply not possible in a digital world that my signature is the same for all documents that I want to sign.


![](https://d2mxuefqeaa7sj.cloudfront.net/s_B9864D4913735962AC3DE2BAA0D3BFE8B8192C1A5FD3A5D869FB844E4A174363_1524991947764_digital-signature.png)


We're gonna talk about how to construct digital signatures in later articles. It's really quite an interesting primitive and we'll see exactly how to do it. Just to give you a hint, the way digital signatures work is basically by making the digital signature via function of the content being signed. So an attacker who tries to copy my signature from one document to another is not gonna succeed because the signature on the new document is not gonna be the proper function of the data in the new document, and as a result, the signature won't verify. And as I said, we're gonna see exactly how to construct digital signatures later on and then we'll prove that those constructions are secure.


- **Anonymous Communication**



![](https://d2mxuefqeaa7sj.cloudfront.net/s_B9864D4913735962AC3DE2BAA0D3BFE8B8192C1A5FD3A5D869FB844E4A174363_1524992424825_anonymous_communication.png)


 Another application of cryptography that I wanted to mention, is anonymous communication. So, here, imagine user Alice wants to talk to some chat server, Bob. And, perhaps she wants to talk about a medical condition, and so she wants to do that anonymously, so that the chat server doesn't actually know who she is. Well, there's a standard method, called a mixnet, that allows Alice to communicate over the public internet with Bob through a sequence of proxies such that at the end of the communication Bob has no idea who he just talked to. The way mixnets work is basically as Alice sends her messages to Bob through a sequence of proxies, these messages get encrypted and decrypted appropriately so that Bob has no idea who he talked to and the proxies themselves don't even know that Alice is talking to Bob, or that actually who is talking to whom more generally. One interesting thing about this anonymous communication channel is, this is bi-directional. In other words, even though Bob has no idea who he's talking to, he can still respond to Alice and Alice will get those messages. Once we have anonymous communication, we can build other privacy mechanisms.


- **Anonymous Digital Cash**

 And I wanna give you one more example which is called anonymous digital cash. Remember that in the physical world if I have a physical dollar, I can walk into a bookstore and buy a book and the merchant would have no idea who I am. The question is whether we can do the exact same thing in the digital world. In the digital world, basically, Alice might have a digital dollar, a digital dollar coin. And she might wanna spend that digital dollar at some online merchants, perhaps some online bookstore. Now, what we'd like to do is make it so that when Alice spends her coin at the bookstore, the bookstore would have no idea who Alice is. So we provide the same anonymity that we get from physical cash.





![](https://d2mxuefqeaa7sj.cloudfront.net/s_B9864D4913735962AC3DE2BAA0D3BFE8B8192C1A5FD3A5D869FB844E4A174363_1524994227866_anonymous_digital_cash.jpg)





 Now the problem is that in the digital world, Alice can take the coin that she had, this one dollar coin, and before she spent it, she can actually make copies of it. And then all of a sudden instead of just having just one dollar coin now all of a sudden she has three dollar coins and they're all the same of course, and there's nothing preventing her from taking those replicas of a dollar coin and spending it at other merchants. And so the question is how do we provide anonymous digital cash? But at the same time, also prevent Alice from double spending the dollar coin at different merchants. In some sense there's a paradox here where anonymity is in conflict with security because if we have anonymous cash there's nothing to prevent Alice from double spending the coin and because the coin is anonymous we have no way of telling who committed this fraud. And so the question is how do we resolve this tension. And it turns out, it's completely doable. And we'll talk about anonymous digital cash later on. Just to give you a hint, I'll say that the way we do it is basically by making sure that if Alice spends the coin once then no one knows who she is, but if she spends the coin more than once, all of a sudden, her identity is completely exposed and then she could be subject to all sorts of legal problems. And so that's how anonymous digital cash would work at a high level and we'll see how to implement it in later articles.
