# beginner-cadence-course

## Chapter 1 Day 1

1. An openly visible and decentralized database anyone can interact with. https://www.investopedia.com/terms/b/blockchain.asp

2. A smart contract is a piece of code that executes and runs either a transaction (updates state) or a script (reads state) of a blockchain. Once a smart contract is deployed on the blockchain it will then execute the actions that were written inside of the contract. note that they don’t necessarily run a script or transaction; instead once deployed they simply execute the set of actions written inside
https://www.ibm.com/topics/smart-contracts

3. a transaction (updates state on-chain) and costs gas and a script (reads state) of a blockchain and is free.

## Chapter 1 Day 2

1. 
-Safety and Security: Every Smart Contract must be secure. Cadence maximizes efficiency while maintaining the highest levels of safety and security. It accomplishes this because of its insanely strong type system, separation between contracts and transactions, and Resource Oriented Programming.

-Clarity: Code should be easy to read, especially Smart Contract code so that we, as users, can verify it is safe. This is achieved by making the code declarative and allowing the developer to express their intentions directly. Cadence makes those intentions very clear by design, which, along with readability, make auditing and reviewing more efficient.

-Approachability: The way Cadence is written is very familiar to other programming languages, making it easy to transition to if you have prior experience.
Developer Experience: The developer should be able to debug in an easy manner, understand what does where, and not feel frustrated. Cadence does this by making error messages very clear.

-Resource Oriented Programming: This is by far the most important, Cadence at its core uses things called Resources, and they define pretty much everything we do on Flow. Everything is a resource.

2. Ease of adoption, best practices, clearly solving existing issues because of Cadence’s ‘Safety and Security’ pillar that, developers can focus solely on building their contract without having to worry about there being any security exploits in their contracts. 5 pillars are useful because they make life easier for both users and developers. Developers can easily transition to it due to its similarity with other programming languages, and it's easy to debug. Users on the other hand can easily read the code because of it's clarity if they're checking the safety of a Contract.

## Chapter 2 Day 1

1.
![chapter2day1quest1](https://user-images.githubusercontent.com/16437897/178188491-0007c41a-1eca-4022-a30d-9e72a806b39f.png)

2.
![chapter2day1quest2](https://user-images.githubusercontent.com/16437897/178188555-41fe148b-e8f5-4f14-bb1d-b2224a588b1b.png)

## Chapter 2 Day 2

1. Because the function changeGreeting would update the state onchain and therefore be a transaction and require gas and signing.

2. AuthAccount is allowing the transaction to access the variables stored in the account during the prepare phase and perhaps modify it before passing it to the execute phase.  because of Cadence’s ‘Safety and Security’ pillar that, developers can focus solely on building their contract without having to worry about there being any security exploits in their contracts. 

3. Prepare runs before the execute and really is just a way of separating the logic in our code making it easier to read.

4.

![Screen Shot 2022-07-12 at 10 21 49 AM](https://user-images.githubusercontent.com/16437897/178560891-094c355b-3dae-430e-806f-eddc22ea3eb3.png)

![Screen Shot 2022-07-12 at 10 22 02 AM](https://user-images.githubusercontent.com/16437897/178560858-a1885c78-cf7c-45ac-b278-3db3e5c4d75e.png)

![Screen Shot 2022-07-12 at 10 25 01 AM](https://user-images.githubusercontent.com/16437897/178560609-11b3eaab-aed2-440c-a46a-ee882088b37b.png)

![Screen Shot 2022-07-12 at 10 25 12 AM](https://user-images.githubusercontent.com/16437897/178560815-cefa9844-2b63-4f8a-93a8-8d37d9a972ac.png)

## Chapter 2 Day 3

1.
![Screen Shot 2022-07-12 at 11 37 14 AM](https://user-images.githubusercontent.com/16437897/178571361-2ef585da-8800-44e7-82f2-bbc6483a17f7.png)


2.
```
pub fun main(): {
  var favouriteNums: {String: UInt64} = {"Facebook": 0, "Instagram": 0, "Twitter": 0, "YouTube":  10, "Reddit": 0, "LinkedIn": 10}
  log(favouriteNums.values)
}
```

3. The force unwrap of an optional makes it a more stringent typeas it no longer is true when nil
```
pub fun main(): Int {
    let hellos: {String: Int} = {"Hi": 1, "Bonjour": 2, "Hola": 3}
    return hellos["Bonjour"]! // we are force-unwrapping the optional
}
```
... this will `panic` and abort the program if there is no value at the "Bonjour" key.
```
pub fun main(): Int? { // notice the return value is an optional type
    let hellos: {String: Int} = {"Hi": 1, "Bonjour": 2, "Hola": 3}
    hellos.remove(Key: "Bonjour")
    return hellos["Bonjour"] // we leave the optional this will accept `nil`
    return hellos["Bonjour"]! // will panic here as we removed "Bonjour"key
}
```

4. We're expecting to return a type String but instead it's returning a type optional.

Two ways you can fix this dependong on your intention.
```
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

## Chapter 3 Day 1

## Chapter 3 Day 2

## Chapter 3 Day 3

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
