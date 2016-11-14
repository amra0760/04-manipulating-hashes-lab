# Manipulating Hashes: Lab

## Objectives

In this lesson, we'll be manipulating some multidimensional hashes.

### Before you jump in
You're going to iterate through the levels of this hash to operate on one of the ice cream flavor arrays from the previous reading. 

**Reminder:** *Iterating through nested hashes is hard, and (I'm pretty sure) you are not psychic. Meaning, you can't necessarily predict with perfect clarity what the key/value pair is at a certain level of the hash.* ***If you need to, use `binding.pry`*** *when you are iterating in upcoming labs to make sure you understand what the key/value pair is that you are iterating over.* If you are confused about using `binding.pry`, you could use `puts` as a less-than-ideal alternative.


### Code Along Challenge I: Manipulating Nested Hashes

Fork and clone this lab. You'll be coding your solution to this first challenge in `lib/first_challenge.rb`. 

Your good buddy Freddy Mercury has recently developed a strawberry allergy! You need to delete `"strawberry"` from his list of favorite ice cream flavors. In the `first_challenge` method, we've given you the hash from our previous example. 

* Iterate over the `contacts` hash and when you reach the key of `:favorite_icecream_flavors`, remove `"strawberry"` from the array of Freddy's favorite ice cream flavors. There are at least two ways you can accomplish this:
  * You can iterate through the hash and, when you reach the appropriate level, check to see if the key `==` ("is equal to") `:favorite_icecream_flavors`. If it does, check to see if that array contains `"strawberry"`. If it does, then delete it from the array. 
  * OR you can directly iterate over the hash that is the value of the `"Freddy Mercury"` key by calling an enumerator method in `contacts["Freddy Mercury"]`.  
  * PRO-TIP: Try doing it both ways!
 
**Hint:** *Use the* `.delete_if` *method to eliminate strawberry from the appropriate array.*  
**Hint:** *Remember that the* `first_challenge` *method needs to return the newly altered* `contacts` *hash.*

## Higher Level Hash Methods

In a previous lab, you were asked to iterate over a hash and collect the key that pointed to the lowest value. We asked you not to use some of the higher level hash methods there. Now, we're going to learn a few tricks that can make a task like that much easier. 

### `.values`

You can collect all of the values in a hash with the `.values` method: 

```ruby
family_members = {mom: "Victoria", dad: "Richard", sister: "Zoe"}

family_members.values
#  => ["Victoria", "Richard", "Zoe"]
```

We can see that the `.values` method returns an array of the values of the keys in the hash. 

### `.keys`

This method, not surprisingly, returns an array containing all of the keys in the hash that `.keys` has been called on: 

```ruby
family_members = {mom: "Victoria", dad: "Richard", sister: "Zoe"}

family_members.keys
#  => [:mom, :dad, :sister]
```

### `.min`

You can use the .min method on a hash to return the key/value pair that contains that **lowest key**, either alphabetically or numerically:

```ruby
food_items = {apples: 45, pears: 12}

food_items.min
#  => [:apples, 45] 
```

These are only a few of the many helpful methods out there. Be sure to check out the [Ruby Docs on Hashes](http://ruby-doc.org/core-2.2.2/Hash.html) to learn more. 

Let's practice before you move on to the next challenge: 


### Code Along Challenge II: Manipulating Nested Hashes

You'll be coding your solution to this challenge in `lib/second_challenge.rb`. In the `second_challenge` method we have a nested hash of grocery items. 

* Use the `.values` method to collect all of the values of the grocery type keys (`:dairy`, `:vegetables`, `:meat`, `:grains`). The method should return a *one-dimensional* (or "flat") array that *only* includes  the values (groceries such as "milk" and "carrots") without their keys. 

**Hint:** What happens when you call `.values` on a nested hash? What is the return value? How can you *flatten* an array of arrays? Make sure to use `binding.pry` to help you solve this one. 


## Resources: 

* [Ruby Docs on Hashes](http://ruby-doc.org/core-2.2.0/Hash.html)