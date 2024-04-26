---
layout: page
title: Actor Model
description: Concurrent computation framework
img: assets/img/cartoon-actors.jpg
importance: 5
category: fun
---

The actor model is a principled way to address the needs of modern distributed systems, allowing great flexibility and scalability.
Its development has been very much influenced by physics, and motivated by the growing availability of highly parallel computing machines. 
Also, this model has been influential on both mathematical formulations of computational systems, and practical software engineering.

The design of many techniques used in software often comes from observation of real world phenomena. Actor model makes no exception.
Almost all species inhabiting earth have learnt their way to share information and mobilise individual and collective actions.
Through effective communication, individuals can organize theirselves in groups and coordinate complex tasks that cannot be taken alone. 
For this reason, communication has always played a pivotal role in every aspects of our lives.

Analogously to the regular daily interactions and connections between individuals, the actor model allows to think about the code
in terms of communication between different entities named the actors. 
The actor is the building block of the model, a truly independent computational unit with its own local memory. 
An actor owns a private state, knows how to create and dispose itself, and can send and receive messages to other actors. 
Upon message receival, the actor safely stores the message in an internal queue, so that when its turn arrives, 
it starts being processed, which can sometimes involve a state update, and at the end a result is delivered with a reply message.

An important difference between actors and objects is that while object method can be called by many threads, an actor can process
the messages sent to it sequentially, one after the other. 
Additionally, sending a message does not transfer the thread of execution from the sender to the receiver. Conversely, both the sender 
and the receiver actors can interact indirectly by exchanging messages. This removes the need of synchronizating different threads 
of execution with costly locking techniques. 

During my spare time I have developed a toy framework implementing all principles above and enabling web applications to be developed
following the actor model. Please have a look at my <a href="https://github.com/amuolo/data-management">data management repository</a>.







