# beginner-cadence-course

## Chapter 1 Day 1

1. -Q:  Explain what the Blockchain is in your own words.

An openly visible and decentralized database anyone can interact with. https://www.investopedia.com/terms/b/blockchain.asp

2. -Q:  Explain what a Smart Contract is.

A smart contract is a piece of code that executes and runs either a transaction (updates state) or a script (reads state) of a blockchain. Once a smart contract is deployed on the blockchain it will then execute the actions that were written inside of the contract. note that they don’t necessarily run a script or transaction; instead once deployed they simply execute the set of actions written inside (like a rulebook)
https://www.ibm.com/topics/smart-contracts

3. -Q:  Explain the difference between a script and a transaction.

a transaction (updates state on-chain) and costs gas and a script (reads state) of a blockchain and is free.

## Chapter 1 Day 2

1. -Q: What are the 5 Cadence Programming Language Pillars?
-Safety and Security: Every Smart Contract must be secure. Cadence maximizes efficiency while maintaining the highest levels of safety and security. It accomplishes this because of its insanely strong type system, separation between contracts and transactions, and Resource Oriented Programming.

-Clarity: Code should be easy to read, especially Smart Contract code so that we, as users, can verify it is safe. This is achieved by making the code declarative and allowing the developer to express their intentions directly. Cadence makes those intentions very clear by design, which, along with readability, make auditing and reviewing more efficient.

-Approachability: The way Cadence is written is very familiar to other programming languages, making it easy to transition to if you have prior experience.
Developer Experience: The developer should be able to debug in an easy manner, understand what does where, and not feel frustrated. Cadence does this by making error messages very clear.

-Resource Oriented Programming: This is by far the most important, Cadence at its core uses things called Resources, and they define pretty much everything we do on Flow. Everything is a resource.

2. -Q: In your opinion, even without knowing anything about the Blockchain or coding, why could the 5 Pillars be useful (you don't have to answer this for #5)?

Ease of adoption, best practices, clearly solving existing issues because of Cadence’s ‘Safety and Security’ pillar that, developers can focus solely on building their contract without having to worry about there being any security exploits in their contracts. 5 pillars are useful because they make life easier for both users and developers. Developers can easily transition to it due to its similarity with other programming languages, and it's easy to debug. Users on the other hand can easily read the code because of it's clarity if they're checking the safety of a Contract.

## Chapter 2 Day 1

1.
![chapter2day1quest1](https://user-images.githubusercontent.com/16437897/178188491-0007c41a-1eca-4022-a30d-9e72a806b39f.png)

2.
![chapter2day1quest2](https://user-images.githubusercontent.com/16437897/178188555-41fe148b-e8f5-4f14-bb1d-b2224a588b1b.png)

## Chapter 2 Day 2

1. -Q: Explain why we wouldn't call changeGreeting in a script.

Because the function changeGreeting would update the state onchain and therefore be a transaction and require gas and signing.

2. -Q: What does the AuthAccount mean in the prepare phase of the transaction?

AuthAccount is allowing the transaction to access the variables stored in the account during the prepare phase and perhaps modify it before passing it to the execute phase.  because of Cadence’s ‘Safety and Security’ pillar that, developers can focus solely on building their contract without having to worry about there being any security exploits in their contracts. 

3. -Q:What is the difference between the prepare phase and the execute phase in the transaction?

Prepare runs before the execute and really is just a way of separating the logic in our code making it easier to read. The prepare phase is used to access data in the authorizers account, while the execute phase is used to call functions that change/modify the data in theaccount.

4.

![Screen Shot 2022-07-12 at 10 21 49 AM](https://user-images.githubusercontent.com/16437897/178560891-094c355b-3dae-430e-806f-eddc22ea3eb3.png)

![Screen Shot 2022-07-12 at 10 22 02 AM](https://user-images.githubusercontent.com/16437897/178560858-a1885c78-cf7c-45ac-b278-3db3e5c4d75e.png)

![Screen Shot 2022-07-12 at 10 25 01 AM](https://user-images.githubusercontent.com/16437897/178560609-11b3eaab-aed2-440c-a46a-ee882088b37b.png)

![Screen Shot 2022-07-12 at 10 25 12 AM](https://user-images.githubusercontent.com/16437897/178560815-cefa9844-2b63-4f8a-93a8-8d37d9a972ac.png)

## Chapter 2 Day 3

1.
![Screen Shot 2022-07-12 at 11 37 14 AM](https://user-images.githubusercontent.com/16437897/178571361-2ef585da-8800-44e7-82f2-bbc6483a17f7.png)


2.
```Cadence
pub fun main(): {
  var favouriteNums: {String: UInt64} = {"Facebook": 0, "Instagram": 0, "Twitter": 0, "YouTube":  10, "Reddit": 0, "LinkedIn": 10}
  log(favouriteNums.values)
}
```

3. The force unwrap of an optional makes it a more stringent typeas it no longer is true when nil
```Cadence
pub fun main(): Int {
    let hellos: {String: Int} = {"Hi": 1, "Bonjour": 2, "Hola": 3}
    return hellos["Bonjour"]! // we are force-unwrapping the optional
}
```
... this will `panic` and abort the program if there is no value at the "Bonjour" key.
```Cadence
pub fun main(): Int? { // notice the return value is an optional type
    let hellos: {String: Int} = {"Hi": 1, "Bonjour": 2, "Hola": 3}
    hellos.remove(Key: "Bonjour")
    return hellos["Bonjour"] // we leave the optional this will accept `nil`
    return hellos["Bonjour"]! // will panic here as we removed "Bonjour"key
}
```

4. We're expecting to return a type String but instead it's returning a type optional.

Two ways you can fix this dependong on your intention.
```Cadence
pub fun main(): String {
let thing: {Address:String} = {0x01: "One", 0x02: "Two", 0x03: "Three"}
return thing[0x03]! // this will unwrap the optional and give the value
}
```
or
```
pub fun main(): String? {
let thing: {Address:String} = {0x01: "One", 0x02: "Two", 0x03: "Three"}
return thing[0x03] this will give keep the optional an
```

## Chapter 2 Day 4

1.-5.
![Screen Shot 2022-07-12 at 2 24 16 PM](https://user-images.githubusercontent.com/16437897/178598757-f509c524-1e04-41ea-a3d7-c6e4eb73e847.png)

![Screen Shot 2022-07-12 at 2 24 25 PM](https://user-images.githubusercontent.com/16437897/178598778-bc38907c-8818-4747-abe0-ea8f63a92868.png)

![Screen Shot 2022-07-12 at 2 24 41 PM](https://user-images.githubusercontent.com/16437897/178598640-8fdd43ae-3ddd-42fa-a5e6-b54d52afdea6.png)


## Chapter 3 Day 1

1.
They cannot be copied
They cannot be lost (or overwritten)
They cannot be created whenever you want
You must be extremely explicit about how you handle a resource (for example, moving them)
Resources are much harder to deal with

2. whenever you need to create something important that shouldn't be easy to delete. example: debt certificate. Structs are containers of data. That's it. Resources are extremely secure, hard to lose, impossible to copy, well kept-track-of containers of data that cannot be lost.

3. the create keyword coupled with the declaration format below
```Cadence
 pub resource Jacob {
        pub let rocks: Bool
        init() {
            self.rocks = true
        }
    }
```

4. If there isn't a public function to create one you cannot make on in an transaction or scipt unless you properly destroy it

5. Public resource of type @Jacob

6.
```Cadence
pub fun createJacob(): @Jacob { // there is 1 here (@)
        let myJacob <- create Jacob() // there are 2 here (arrow and create)
        return <- myJacob // there is 1 here (arrow)
    }
```

## Chapter 3 Day 2

```Cadence
pub contract ResourceIOU {

    pub var dictionaryOfIous: @{UInt64: Iou}
    pub var arrayOfIous: @[Iou]

    pub resource Iou {
        pub let principal: UInt64
        // pub let ower: Address
        // pub let owee: Address
        // pub let unit: String
        // pub let interest: Bool
        init() {
            self.principal = 10
            //self.ower = 0x01
            //self.owee = 0x02
            //self.unit = "usdc"
            //self.interest = false
        }
    }

    // functions
    pub fun addIou(iou: @Iou) {
        let key = iou.principal
        
        let oldIou <- self.dictionaryOfIous[key] <- iou
        destroy oldIou
    }

    pub fun removeIou(index: UInt64): @Iou {
        let iou <- self.dictionaryOfIous.remove(key: index) ?? panic("Could not update the IOU!")
        return <- iou
    }

     pub fun addIouArray(iou: @Iou) {
        self.arrayOfIous.append(<- iou)
    }

    pub fun removeIouArray(index: Int): @Iou {
        return <- self.arrayOfIous.remove(at: index)
    }


    init() {
        self.dictionaryOfIous <- {}
        self.arrayOfIous <- []
    }

}
```

## Chapter 3 Day 3

1. -Q: Define your own contract that stores a dictionary of resources. Add a function to get a reference to one of the resources in the dictionary.

```Cadence
pub contract myRefEx {

    pub var dictionaryOfTokens: @{String: Token}

    pub resource Token {
        pub let ticker: String
        init(_ticker: String) {
            self.ticker = _ticker
        }
    }

    pub fun getReference(key: String): &Token? {
        return (&self.dictionaryOfTokens[key] as &Token?)!
    }

    init() {
        self.dictionaryOfTokens <- {
            "usdc": <- create Token(_ticker: "USDC"), 
            "flow": <- create Token(_ticker: "FLOW")
        }
    }
}
```

2. -Q: Create a script that reads information from that resource using the reference from the function you defined in part 1.

```Cadence
pub contract myRefEx {

    pub var dictionaryOfTokens: @{String: Token}

    pub resource Token {
        pub let ticker: String
        init(_ticker: String) {
            self.ticker = _ticker
        }
    }

    pub fun getReference(key: String): &Token {
        return (&self.dictionaryOfTokens[key] as &Token?)!
    }

    init() {
        self.dictionaryOfTokens <- {
            "usdc": <- create Token(_ticker: "USDC"), 
            "flow": <- create Token(_ticker: "FLOW")
        }
    }
}
```
script:
```Cadence
import myRefEx from 0x02

pub fun main(): String {
  let ref = myRefEx.getReference(key: "usdc")
  return ref.ticker // playgorund giving em an error but i cant see it?
}
```
3. References are useful because you can use pieces of the data in the resource in your code without actually having to load that entire resource.

## Chapter 3 Day 4

## Chapter 3 Day 5

## Chapter 4 Day 1

## Chapter 4 Day 2

## Chapter 4 Day 3

## Chapter 4 Day 4

## Chapter 5 Day 1

## Chapter 5 Day 2

## Chapter 5 Day 3

## Chapter 6 Day 1

## Chapter 6 Day 2

## Chapter 6 Day 3
