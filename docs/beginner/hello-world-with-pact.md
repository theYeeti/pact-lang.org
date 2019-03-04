# **Hello World with Pact**

In this tutorial you will build a "Hello World" smart contract using Pact.

In this tutorial, we’ll introduce Pact, explain some of its core features, and help you take your first steps toward becoming a Pact smart contract developer.

**This tutorial covers the following topics:**

* Hello World Overview
* Create a Keyset
* Create the Module
* Define a Function
* Do The Hello World Dance
* Say Hello World!
* Load Contract into the REPL

The goal is to help you get familiar with the important Pact concepts needed to create a smart contract. This will help you get comfortable as we explore more complicated topics later in the series.

!!! Summary "Key Takeaway"
    Pact smart contracts are made up of keysets and modules. Keysets define who has access to the contract and modules define the logic of the smart contract.
___

## **Hello World with Pact Tutorial**
The following video covers everything you need to get you up and running with your “Hello World” Pact smart contract. You can also follow this tutorial using the text provided below the video.

<div align="center">
   <iframe width="720" height="405" src="https://www.youtube.com/embed/NpEaa2P7qZI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

*Subscribe to [our YouTube channel](https://www.youtube.com/channel/UCB6-MaxD2hlcGLL70ukHotA) to access the latest Pact tutorials.*

___

## **Code Overview**

Before getting into the details of the smart contract, it’s important to take a look at the code you will write.

Navigate to the Pact online editor at [pact.kadena.io/](pact.kadena.io/) to get started. Once on the site you should see the code shown below. You can also copy and paste this code into your editor if needed.

``` Clojure
;;
;; "Hello, world!" smart contract/module
;;

;;---------------------------------
;;
;;  Create an 'admin-keyset' and add some key, for loading this contract!
;;
;;  Make sure the message is signed with this added key as well.
;;
;;---------------------------------

;; Keysets cannot be created in code, thus we read them in
;; from the load message data.
(define-keyset 'admin-keyset (read-keyset "admin-keyset"))

;; Define the module.
(module helloWorld 'admin-keyset
  "A smart contract to greet the world."
  (defun hello (name)
    "Do the hello-world dance"
    (format "Hello {}!" [name]))
)

;; and say hello!
(hello "world")
```
This code can also be found [here](https://github.com/kadena-io/pact-examples/tree/master/hello-world) on our GitHub.
___


### **Create a Keyset**

To start your smart contract you’ll need to define a keyset. [Keysets](https://pact-language.readthedocs.io/en/latest/pact-reference.html#confidential-keysets) specify authorization to different parts of the code. They to determine which accounts have access to which parts of the program.

Line 16 (shown below) defines and reads a keyset named admin-keyset. 

``` Clojure
(define-keyset 'admin-keyset (read-keyset "admin-keyset"))
```

If you look to the left of this line you will notice the following error. 

!!! Error
      No such key in message: admin-keyset.

This error is exists because you are reading in a keyset that you have not created yet. To get rid of this error you will need to create a keyset named admin-keyset.

**Follow the steps below to create a keyset:**

* On the right panel navigate to **ENV > Data > Keysets**

* Enter `admin-keyset`

You have now created the keyset being read by your contract. The error message should no longer exist.


___

### **Define the Module**
Now that you have created a keyset, it’s time to write the module for your smart contract. [Modules](https://pact-language.readthedocs.io/en/latest/pact-reference.html#module-declaration) are very important in Pact. They contain all of the logic needed to run your smart contract. 

The syntax used to create a module is shown below. This line defines a module named `helloWorld` and gives the `admin-keyset` access to this module.

``` Clojure
module helloWorld 'admin-keyset
```

### **Define a Function**

Defining functions is an important part of creating a module in Pact. For your Hello World smart contract, you’ll need to define a function named hello that takes a parameter called `name`.

This can be done using the line shown below. As you can see, a function is defined in Pact using the keyword `defun`.

``` Clojure
"A smart contract to greet the world."
(defun hello (name)
```
___

### **Do the Hello World Dance**

In the final line of the module you will write the output to the REPL. You can do this using the keyword format. Format allows you to manipulate strings and will help you get the correct output. 

``` Clojure
"Do the hello-world dance"
format "Hello {}!" [name]
```

This line outputs a string to the REPL that says `Hello` followed by whatever is specified by the function parameter `name`.

This line completes the module for this smart contract! While this module is pretty simple, it gives you a great start to begin building more complex smart contracts. 

___

### **Say Hello World!**

The last step to write “Hello World” to the REPL is to call the function defined in the module. You can do this using the line shown below.

``` Clojure
;; and say hello!
(hello "world")
```

This line calls the function `hello` and specifies the name as `“world”`. 


___
### **Load Contract Into the REPL**

The final section of this contract specifies its output. 

To do this, concatenate the word `Hello` with the input to the function created previously.

``` Clojure
"Do the hello-world dance"
(format "Hello {}!" [name])
```

Given the input `World`, this smart contract will now output the message `Hello World`.

!!! Note
      Strings are formatted in Pact using the keyword `format`.

___

### **Load into REPL**

Now that your smart contract is written, you are ready to load it into the REPL.

To do this, select the **Load into REPL** button at the top of your editor. If everything is working you will see the REPL open up on the right side of your screen with the `Hello World` message as shown below.

``` Clojure
;; Welcome to the Pact interactive repl
;; Use 'LOAD into REPL' button to execute editor text
;; then just type at the "pact>" prompt to interact!
;;
;; To reset the REPL type 'reset'!
Hello world!
pact>

```

Congratulations! You have completed your Hello World smart contract with Pact. If you would like, try changing “world” to say something else. You can also try changing the keysets, defining new functions, or experimenting however you’d like.


___

## **Review**

This tutorial helped you get up and running with your Hello World smart contract with Pact. It introduced important concepts like keysets, modules, defun, and format. At this point, you are ready to explore more advanced concepts to begin creating more complex smart contracts.

Leave a comment below if you have any questions or move on to the next tutorial to learn more about the Pact programming language.

___





