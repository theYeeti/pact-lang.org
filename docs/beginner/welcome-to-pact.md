# **Welcome to Pact**

Welcome to the Pact smart contract programming language!

In this tutorial, we’ll introduce Pact, explain some of its core features, and help you take your first steps toward becoming a Pact smart contract developer.

**Topics covered in this tutorial**

* Introduction to Pact
* Pact Key Features
* Other Features
* Learn More About Pact

The goal is to familiarize you with what Pact is, what it is used for, and some key decisions that influenced the design of this new language.

!!! Summary "Key Takeaway"
    Pact is the safest, most user-friendly language for smart contracts. It’s designed for security and performance. It is turing incomplete, human readable, supports upgradable contracts, and formal verification to make high performant and secure smart contracts.

___

## **Welcome to Pact Tutorial**
The following video covers some important details of the Pact programming language. You can also follow this tutorial using the text provided below the video.

<div align="center">
   <iframe width="720" height="405" src="https://www.youtube.com/embed/NpEaa2P7qZI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

Subscribe to our [YouTube channel](https://www.youtube.com/channel/UCB6-MaxD2hlcGLL70ukHotA) to access the latest Pact tutorials!
___

## **Welcome to Pact**
Pact is an open-source programming language for writing **smart contracts**. 

It’s designed from the ground up to support the unique challenges of developing solutions to run on a blockchain. Pact empowers developers to create robust and high performance logic for transactions. It facilitates execution of mission-critical business operations quickly and effectively. 


![welcome-to-pact](assets/beginner-tutorials/welcome-to-pact/pact-smart-contracts.png)

Pact is designed with safety in mind. Its design is informed by existing approaches to smart contracts as well as stored procedure languages like SQL and LISP. Pact resembles a general-purpose, Turing-complete language. It includes LISP-like syntax, user functions, modules, and imperative style. 
___

### **Pact Smart Contracts**

A smart contract in Pact is comprised of three core elements: the code module, keysets, and tables. Each of these will be explored in more detail throughout the series. 

*Here’s a quick overview of each of these core elements.*

|                  |                                                                                                                                                       |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Module**  | A module is where logic is defined for a smart contract. It contains functions, pact definitions, tables, and schemas.                                |
| **Keysets** | Pact Keysets specify authorization to different parts of the smart contract. They determine which accounts have access to which parts of the program. |
| **Tables**  | Data in Pact is stored in tables. These tables have a “key-row” structure and support schemas as well as a versioned, columnar history.               |

___

## **Pact Key Features**
There are many important features that make Pact such a safe and high performance language for creating smart contracts. Here are a few that we’ll focus on throughout this tutorial.

**Pact Key Features**

* Turing incomplete
* Human Readable
* Upgradable Contracts
* Formal Verification

First, Pact is a **turing-incomplete** language with deliberate constraints on its computational ability. This supports its design goal of “just enough” power for transactional blockchain solutions without exposing you to unnecessary attack vectors. 

All Pact code is stored as written in a **human-readable** form on the ledger. It is installed onto the blockchain directly, so you can always review the running code and be sure of exactly what its doing. 

Pact also supports **upgradable contracts** so that you can offer new features, adapt to new workflow requirements, and fix bugs as they are discovered. 

Finally, Pact comes equipped with a powerful validation tool suite in the form of **formal verification**. Pact uses Z3, an open-source tool developed by Microsoft, to mathematically verify and test for bugs present in code.

These features along with it’s excellent tooling ecosystem and developer community makes writing smart contracts with Pact both fun and productive. Let’s explore each of these features in a little more detail.

___

### **Turing Incomplete**

Pact contracts are Turing incomplete.

A Turing complete language has the power to run any possible program. In some languages that’s an extremely important feature. For smart contracts it’s an incredibly dangerous feature. For that reason, Pact is designed to be turing incomplete, which places deliberate constraints on its computational ability. This supports its design goal of “just enough” power for transactional blockchain solutions and helps ensure the security of its smart contracts.

The first restriction in Pact is that there is no unbounded looping or recursion. Pact detects recursion and fails immediately. Looping is also only supported in special circumstances. The key benefits of this is to reduce cost and improve performance. 
This feature makes some of the most infamous and costly bugs discovered in other platforms not even possible with Pact.
For more information on this topic, see our blog post [Turing Completeness and Smart Contract Security](https://medium.com/kadena-io/turing-completeness-and-smart-contract-security-67e4c41704c).

___

### **Human Readable**

Pact smart contracts are human readable.

Smart contracts solve business problems that require both technical and non-technical expertise. To build the best smart contract solution, it’s important for everyone involved to be able to understand and contribute to the development of the smart contract.

For that reason, Pact was built to be simple to read and write. This helps provide complete transparency for the logic within its smart contracts. This approach also encourages shorter programs. Code executes directly on the ledger where it can be read easily by anyone. As a result, Pact is easy to understand.
For example, here’s a “Hello World” smart contract using Pact.

``` clojure
(module helloWorld 'admin-keyset
  (defun hello (name)
    (format "Hello {}!" [name]))
)
(hello "world")
```
Without having learned anything about the Pact language, you can already start to see how it works. We’ll explain more of the terms and syntax in a later tutorial, but with these few simple lines of code, you’re seeing a fully functioning Pact “Hello World” smart contract.

Once written, smart contracts are deployed to a blockchain. In Pact, the code on the blockchain is exactly the same as the code that was written. This means that no matter when you see the code it will always be exactly as it was built. This helps you know exactly what’s going on so you can continue to moderate and improve your application over time. 

___

### **Upgradable Contracts**

Pact contracts are upgradable. 

Upgradable contracts allow you to revise and improve your smart contracts over time. This allows you to offer new features and fix bugs as you continue developing your smart contract. None of this is possible with other smart contract languages, and it’s an extremely helpful feature when trying to build the most impactful application for your business.

The simplicity of upgrading contracts is further amplified by its tooling ecosystem. Compiler and runtime errors offer detailed information, with stack traces and function documentation to ensure you’re making the best version of your smart contract.
Pact’s iterative development process is also supported by a feature-rich REPL helping you to rapidly improve and deploy new smart contracts. It includes features such as incremental transaction execution and environment and database inspection.

___

### **Formal Verification**

Pact is supported by formal verification, a system to mathematically prove that your code is safe.

This means that Pact allows smart contract authors to express, automatically check, and formally verify that their code does not contain any bugs. This is the same system used to protect mission critical environments like nuclear power plants or air and space autopilot systems. You now have this same high level of security in every smart contract you write with Pact.

Formal verification is a huge topic that’s been covered extremely well in the Kadena blog. See our blog post [Pact Formal Verification: Making Blockchain Smart Contracts Safer](https://medium.com/kadena-io/pact-formal-verification-for-blockchain-smart-contracts-done-right-889058bd8c3f) for more information on this topic.
___

## **Other Pact Features**

There are many other features that Pact supports to help make your developer experience as rewarding as possible. These features include type inference, atomic transaction execution, RDBMS integration, confidential computing, and more!

**Type Inference** 

Pact includes type inference. This makes it possible for code to be strongly-typed without declaring type information. It also has the added benefit of limiting run-time type enforcement. Developers can use a typecheck to add “just enough types”. This eliminates warnings and only enforces types at runtime where needed. 

**Atomic Transaction Execution** 

Similar to RDBMS systems, Pact offers the benefit of atomic execution. This allows changes to commit to the database only if the code runs successfully. Any errors roll back changes, abort execution, and avoid costly mistakes.

**RDBMS Integration**

Pact is also designed to allow direct integration with an industrial RDBMS. This is helpful in cases that need efficient publication of historical data. 

**Confidential Computing with “Pacts”**

The Pact programming language is named after one of its key features, known as “Pacts”. “Pacts” solve an important blockchain problem in privacy-preserving blockchains. To maintain privacy on a blockchain, participants can only run a subset of smart contracts. In these cases, the databases of each of the participants become disjointed.

Pact solves this problem using coroutines. Coroutines are functions that can start and stop at key points in a function’s execution. These coroutines are called pacts. They define the steps to be executed by different entities as sequential transactions on the blockchain.

___

## **Learn More**

This is only a few of the important features that make Pact such a powerful language for writing smart contracts. There are many resources available to help you learn more about Pact. To get you started, here’s a list of places you can go.

**Where to go next:**

* Join the [Discord Channel](https://discordapp.com/channels/502858632178958377/502858632178958380) for community discussion.
* Read the [The Pact Smart-Contract Language White Paper](https://kadena.io/docs/Kadena-PactWhitepaper.pdf)to learn more about the creation of Pact.
* Read the [Pact documentation](https://pact-language.readthedocs.io/en/latest/)for a detailed look at everything the language offers. 
* Follow the [Pact GitHub page](https://github.com/kadena-io/pact)for the latest updates on Pact development. 
* Ask questions on [Stack Overflow](https://stackoverflow.com/search?q=pact-lang) using **#pact-lang**.


Along with all of these resources, you can also continue this tutorial series. Throughout these tutorials, you’ll learn all about Pact by walking through each of its features, building real world applications, and exploring new ideas for yourself that take the language in directions no one has even thought of yet. 

Feel free to join the community and reach out if you have any questions. We’re extremely excited to help you start your journey as a Pact smart contract developer. 

___






