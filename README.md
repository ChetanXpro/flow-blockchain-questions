# quest-submissions

# CHAPTER-1 DAY-1


1.Explain what the Blockchain is in your own words.

-> Blockchain was first introduce by a unknown persion named Satoshi Nakamoto in 2008, blockchain is a open , permanent and distributed database which is      spread in  thousands of nodes.
   it is impossible to edit and delete the data on nodes, blockchain store data in chain of blocks and each block contain ledger of all transactions,
   participants can confirm transactions without permissions of central authority.
   usually Central authority can ban any user from their platform but in bloackchain there are no central authority, so users have no restrictions 
   
   
2. Explain what a Smart Contract is.
   
   -> Smart contracts are programs which run on blockchain , 
     A smart contract is a digital agreement that enables two or more parties to exchange money, Nfts etc in a conflict-free way while avoiding the               need for a third party they are enforced by a specific set of rules. These rules are predefined by computer code.
    
3.Explain the difference between a script and a transaction.
  
  -> A transaction can change the data on blockchain thats why it will cost money.
  -> A script can only view data on blockchain and thats why there is not charge for this.
  
  
  
  
 # CHAPTER-1 DAY-2
 
 
 1.What are the 5 Cadence Programming Language Pillars?
 
 - Safety and Security
 - Clarity
 - Approachability
 - Developer Experience
 - Resource Oriented Programming


2.In your opinion, even without knowing anything about the Blockchain or coding

- Safety/Security is the main priority of any language. 
- Clarity: there should be clarity in any language it should be readable , so that any user who dont know programming and atleast he got overview what is   hapnning.  
- approachability: A language should be in such a way that a programmer can realate things whith their prior experience.
- Developer Experience: debugging is the main part of programming, language should be easy to debug , this will save lots of time of devs.

- Resource Oriented Programming: As we know a small mistake in code can lead to million dollar loss , by the help of resources it can be hard for a    developer to made a mistake. this can restrict devs to make mistakes which can lead to major losses of some important nfs etc. 


# Chapter-2 Day 1


1.Deploy a contract to account 0x03 called "JacobTucker". Inside that contract, declare a constant variable named is, and make it have type String. Initialize it to "the best" when your contract gets deployed.

![contract](https://user-images.githubusercontent.com/107798155/189510226-ca5943b2-547f-4ea0-9623-2483208899d7.png)


2.Check that your variable is actually equals "the best" by executing a script to read that variable. Include a screenshot of the output.

![script](https://user-images.githubusercontent.com/107798155/189510337-5e13c872-7904-4911-a7cc-3988e8d3186d.png)


# Chapter-2 Day-2

1.Explain why we wouldn't call changeGreeting in a script.
 
 - because we can only view data with script , to call changeGreeting we have to use transaction.

2.What does the AuthAccount mean in the prepare phase of the transaction?

- AuthAccount is used to access data stored in that account, and it represent the account which sending the transaction.

3.What is the difference between the prepare phase and the execute phase in the transaction?

- In prepare phase we can access user data and can store data and can also execute functions 
- In execute phase we can only call functions we cant access user data.


4. Contract,Transaction,Script.

  ![contract](https://user-images.githubusercontent.com/107798155/189510988-e4ffb1b9-77cd-41c8-8197-b7a6a901b4e7.png)

  ![transaction](https://user-images.githubusercontent.com/107798155/189511021-1d34fa54-e9b4-43cc-a32b-72407593580d.png)
   
  ![script](https://user-images.githubusercontent.com/107798155/189511030-5a25082f-a88e-4c12-8def-e01eba3eb26c.png)
  

# Chapter-2 Day 3

1. In a script, initialize an array (that has length == 3) of your favourite people, represented as Strings, and log it.

- ![array](https://user-images.githubusercontent.com/107798155/193441697-40dfca55-b562-479d-a990-4f184141dc97.png)


2. In a script, initialize a dictionary that maps the Strings Facebook, Instagram, Twitter, YouTube, Reddit, and LinkedIn to a UInt64 that represents the order in which you use them from most to least. For example, YouTube --> 1, Reddit --> 2, etc. If you've never used one before, map it to 0!.

- ![dictionary](https://user-images.githubusercontent.com/107798155/193441724-e2294758-77b3-49c3-9564-f6227c6d2ac6.png)

3. Explain what the force unwrap operator ! does, with an example different from the one I showed you (you can just change the type).

- ! force cadence to not care about errors - like "i know what im doing, theres definitely something here"

- ![!](https://user-images.githubusercontent.com/107798155/193441727-e92847bc-df2b-4d9d-8771-53f89f73d3c3.png)

4. Using this picture below, explain...

  - What the error message means - Code is returning a String optional not a String.
  - Why we're getting this error -  because dictionaries return optinal values
  - How to fix it - Either force unwrap it ( Social[0x03]! ) or change the return type to be an optional ( pub fun main(): String? {} )
  
 - Error picture => <img width="1361" alt="wrongcode" src="https://user-images.githubusercontent.com/107798155/193442011-b81e5652-0749-40a7-8aa8-735566aba888.png">
 

