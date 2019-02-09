# Overview
  There are various implementations of array ( We don't have to worry about it in JS, but these terms are borrowed from Java)

  `ArrayList` - This is the common one we think of when we think of an array / list of some type. They work by interacting directly with an allocated piece of memory

  * Very fast lookup
  * Can be expensive to shift memory locations when we remove an item
  * Optimised for READS

![Local Image](/images/data-structures/ArrayList.png)

  `LinkedList` - Each element contains a "next / data" section, Where the "next" component tells us how to get to our next element

  * Delete are very cheap - We can simply point `deleteIndex-1` next value to be `deleteIndex+1` location
  * Lookups (`GET`) are not contant they are `On`, In a worse case we may have to traverse the entire list

![Local Image](/images/data-structures/LinkedList.png)

# Exercise

  Implement
# Solution

