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

- ! wll say if it is nill then panic and abort the program
- ! force cadence to not care about errors - like "i know what im doing, theres definitely something here"

- ![!](https://user-images.githubusercontent.com/107798155/193441727-e92847bc-df2b-4d9d-8771-53f89f73d3c3.png)

4. Using this picture below, explain...

  - What the error message means - Code is returning a String optional not a String.
  - Why we're getting this error -  because dictionaries return optinal values
  - How to fix it - Either force unwrap it ( Social[0x03]! ) or change the return type to be an optional ( pub fun main(): String? {} )
  
 - Error picture => <img width="1361" alt="wrongcode" src="https://user-images.githubusercontent.com/107798155/193442011-b81e5652-0749-40a7-8aa8-735566aba888.png">


# Chapter-2 Day 4

1. Deploy a new contract that has a Struct of your choosing inside of it (must be different than Profile).
2. Create a dictionary or array that contains the Struct you defined.
3. Create a function to add to that array/dictionary.

```
pub contract Cadence {
pub var mycats:{Address:Cats}
pub struct Cats{

pub var name:String
pub var age:Int


init(_name:String,_age:Int ){
self.name = _name
self.age = _age
}
}


pub fun addcats(name:String,age:Int,account:Address){

self.mycats[account] = Cats(_name:name,_age:age)

}

init(){

self.mycats = {}
}
}
```

4. Add a transaction to call that function in step 3.

```
import Cadence from 0x01

transaction(name:String,age:Int,account:Address){
prepare(signer:AuthAccount){}


execute{

Cadence.addcats(name: name, age: age, account: account)

}

}
```

5. Add a script to read the Struct you defined.

```
import Cadence from 0x01

pub fun main(account:Address): Cadence.Cats{
  return Cadence.mycats[account]!
}

```

# Chapter 3 Day 1 - Resources

1. In words, list 3 reasons why structs are different from resources.
  
  -  resources can't be copied but structs can be copied easily
  -  resources can't be lost, we can  intentionally destroy it.
  -  resources must be created and moved with very intentional, and there is  specific syntax to move resource.

2. Describe a situation where a resource might be better to use than a struct.

  - A resource is useful when the data is very valuable and it will be unique and needs to be carefully tracked, like a NFT.

3. What is the keyword to make a new resource?

  - create

4. Can a resource be created in a script or transaction (assuming there isn't a public function to create one)?

  - No, it has to be done in the contract.

5. What is the type of the resource below?

  ```
  pub resource Jacob {

  }
  ```
 - @Jacob

6. Let's play the "I Spy" game from when we were kids. I Spy 4 things wrong with this code. Please fix them.
 
 Error code
 ```
 pub contract Test {

    // Hint: There's nothing wrong here ;)
    pub resource Jacob {
        pub let rocks: Bool
        init() {
            self.rocks = true
        }
    }

    pub fun createJacob(): Jacob { // there is 1 here
        let myJacob = Jacob() // there are 2 here
        return myJacob // there is 1 here
    }
}
 ```
 
 Correct code
 
 ```
 pub contract Test {

    // Hint: There's nothing wrong here ;)
    pub resource Jacob {
        pub let rocks: Bool
        init() {
            self.rocks = true
        }
    }

    pub fun createJacob(): @Jacob { // added '@' to define resource type
        let myJacob <- create Jacob() // use move operator '<-' and 'create'
        return <- myJacob // use move operator '<-'
    }
}
 ```
 
 
# Chapter 3 Day 2 - Resources in Dictionaries & Arrays

1. Write your own smart contract that contains two state variables: an array of resources, and a dictionary of resources. Add functions to remove and add to each of them. They must be different from the examples above.

```
pub contract Meta{

pub var arrayOfMonkey: @[Monkey]
pub var dictionaryOfMonkey: @{String:ModernMonkey}

pub resource Monkey{

 pub var name:String

 init(){
 self.name = "FunnyMonkey"
 }
}

pub resource ModernMonkey{

 pub let name:String

 init(){
 self.name = "ChingChongMonkey"
 }
}

pub fun addMonkeyInArray(monkey:@Monkey){

 self.arrayOfMonkey.append(<- monkey)

}

pub fun removeMonkeyfromArray(id:UInt64):@Monkey{
 return <- self.arrayOfMonkey.remove(at: id)
}


pub fun addToDictionary(modernMonkey:@ModernMonkey){

 let key = modernMonkey.name

 self.dictionaryOfMonkey[key] <-! modernMonkey
}

pub fun removeFromDictionary(key:String):@ModernMonkey{

 let monkey <- self.dictionaryOfMonkey.remove(key: key) 
                   ?? panic("No resource at this key")

 return <- monkey

}

init(){
 self.arrayOfMonkey <- []
 self.dictionaryOfMonkey <- {}
 }
}
```
 
 
# Chapter 3 Day 3 - References

1. Define your own contract that stores a dictionary of resources. Add a function to get a reference to one of the resources in the dictionary.

- ```
  pub contract Meta{


pub var dictionaryOfMonkey: @{String:ModernMonkey}

pub resource ModernMonkey {

 pub let name:String


 init(){
 self.name = "Chetan"
 }
}

 
pub fun getref(name:String):&ModernMonkey?{

 return (&self.dictionaryOfMonkey[name] as &ModernMonkey?)?? panic("Nothing here")

}


init(){
 
 self.dictionaryOfMonkey <- {
  "MonkeyParty": <- create ModernMonkey()
        }
 }
}
  ```
2. Create a script that reads information from that resource using the reference from the function you defined in part 1.

- ```
  import Meta from 0x01

pub fun main():&Meta.ModernMonkey{

 return (Meta.getref(name: "MonkeyParty")) ?? panic("Nothing here")
 
}

  ```

3. Explain, in your own words, why references can be useful in Cadence.

- We dont have to move resources here and there, we can easily get refereces and then we can read and update data easily.



