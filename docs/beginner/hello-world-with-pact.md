# **Hello World with Pact**

In this tutorial you will build a "Hello World" smart contract using Pact.

**This tutorial covers the following topics:**

* Hello World code overview
* Hello World code deep dive
* Key terms 

It also introduces important ideas that will prepare you to create more complicated smart contracts.

!!! Summary "Key Takeaway"
    The Pact online editor provides boiler plate code that allows you to quickly deploy a “Hello World” smart contract.
___

## **Hello World with Pact Tutorial**
The following video will get you up and running with your “Hello World” Pact smart contract.



<div align="center">
   <iframe width="720" height="405" src="https://www.youtube.com/embed/NpEaa2P7qZI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>

Video currently under development. Prototype version can be found on google drive [here](https://drive.google.com/drive/u/0/folders/1vkb8rrFohGJq2hEUhO-5bVUxYnimB99d).

*Subscribe to [our YouTube channel](https://www.youtube.com/channel/UCB6-MaxD2hlcGLL70ukHotA) to access the latest Pact tutorials.*

___

## **Code Overview**
Navigate to the Pact online editor at [pact.kadena.io/](https://pact.kadena.io) to get started.

The following code should be available from within the online editor.

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

## **Code deep dive**
Pact smart contracts have 3 main sections; the **keyset**, the **module**, and the **output**. 

### **Keyset**

[Keysets](https://pact-language.readthedocs.io/en/latest/pact-reference.html#confidential-keysets) specify authorization to different parts of the code. They are what allow you to determine which accounts have access to which parts of the program.

You can define and read the `admin-keyset` at the top of the smart contract. This restricts access to the smart contract to this specific keyset.

``` Clojure
(define-keyset 'admin-keyset (read-keyset "admin-keyset"))
```

To access this keyset you need to first create it using the online editor.

Navigate to **ENV > Data > Keysets** and enter **admin-keyset** to create the `admin-keyset`.

!!! Error
      If you do not create the admin-keyset you will continue seeing an error on line 16 of your smart contract.

___
### **Module**
[Modules](https://pact-language.readthedocs.io/en/latest/pact-reference.html#module-declaration) contain the API and data definitions for smart contracts. In this section, you will create the module for this smart contract.

To get started, create a module named `helloWorld` and give access to the `admin-keyset`.

``` Clojure
(module helloWorld 'admin-keyset
```

Next, define a function named `hello` that takes a parameter called `name`. 

``` Clojure
  "A smart contract to greet the world."
  (defun hello (name)
```

!!! Note
      Functions are defined in Pact using the keyword `defun`.

This completes the module for this smart contract. While this module is simple, they can get more complex as you begin building more features into your smart contract.

___
### **Output**

The final section of this contract specifies its output. 

To do this, concatenate the word `Hello` with the input to the function created previously.

``` Clojure
    "Do the hello-world dance"
    (format "Hello {}!" [name]))
)
```

Given the input `World`, this smart contract will now output the message `Hello World`.

!!! Note
      Strings are formatted in Pact using the keyword `format`.

___

### **Load into REPL**

This contract is now ready to Load into the REPL. 

To do this, select the **Load into REPL** button at the top of your editor. 

``` Clojure
;; Welcome to the Pact interactive repl
;; Use 'LOAD into REPL' button to execute editor text
;; then just type at the "pact>" prompt to interact!
;;
;; To reset the REPL type 'reset'!
Hello world!
pact>

```

If done correctly, you will see the REPL open up on the right side of your screen with the `Hello World` message as shown above. 


!!! Tip
      Try changing the `input` to view different outputs in the REPL.
___

## **Key Terms**

Now that you've created your contract, review each of the key terms introduced throughout the tutorial.

!!! Info "Key Terms"
      **Smart Contract**: Self executing contracts that are written in code.

      **Keyset**: Specifies authorization to different parts of the code. 

      **Modules**: Contain the API and data definitions for smart contracts.
      
      **defun**: This keyword is used to define a function in Pact.

These terms will be important as you continue developing smart contracts with Pact.
___

## **Knowledge Check**

<iframe src="https://h5p.org/h5p/embed/429061" width="1090" height="426" frameborder="0" allowfullscreen="allowfullscreen"></iframe><script src="https://h5p.org/sites/all/modules/h5p/library/js/h5p-resizer.js" charset="UTF-8"></script>

___



## **Review**

Congratulations on reaching the end of this tutorial! You should now be up and running with your Pact Hello World smart contract.

**This tutorial covered the following topics:**

* Hello World code overview
* Key terms 
* Hello World code deep dive

!!! Note
      If you have any questions about these topics feel free to leave a comment below. When you're ready, move on to the next section to learn more about the Pact programming language.

___



