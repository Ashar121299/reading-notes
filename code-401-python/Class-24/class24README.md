## HashTables

### What is a Hashtable?

A hash is the result of some algorithm taking an incoming string and converting it into a value that could be used for either security or some other purpose.
In the case of a hashtable, it is used to determine the index of the array.

### Why do we use them?

1.Hold unique values

2.Dictionary

3Library

### What Are they

Hashtables are a data structure that utilize key value pairs. This means every Node or Bucket has both a key, and a value.

The basic idea of a hashtable is the ability to store the key into this data structure, and quickly retrieve the value. This is done through what we call a hash.
A hash is the ability to encode the key that will eventually map to a specific location in the data structure that we can look at directly to retrieve the value.

Since we are able to hash our key and determine the exact location where our value is stored, we can do a lookup in an O(1) time complexity. This is ideal when quick
lookups are required.


### Structure

#### Hashing

Basically, a hash code turns a key into an integer. It’s very important that hash codes are deterministic: their output is determined only by their input. Hash 
codes should never have randomness to them. The same key should always produce the same hash code.


#### create Hashing

A hashtable traditionally is created from an array. I always like the size 1024. this is important for index placement. After you have created your array of the
appropriate size, do some sort of logic to turn that “key” into a numeric number value. Here is a simplistic hashing algorithm:

1.Add or multiply all the ASCII values together.

2.Multiply it by a prime number such as 599.

3.Use modulo to get the remainder of the result, when divided by the total size of the array.

4.Insert into the array at that index.

### Collisions

A collision occurs when more than one key hashes to the same index in an array. As mentioned earlier, a “perfect hash” will never have any collisions.
To put this into perspective, the worst possible hash is one that hashes every single key to the same exact index of an array. The more keys you have hashed to a 
specific index, the more key/value pair combos you can potentially have.

### Bucket Sizes

Buckets - A bucket is what is contained in each index of the array of the hashtable. Each index is a bucket. An index could potentially contain multiple key/value
pairs if a collision occurs.

Hash Maps can have any number of buckets. If a hash map has only a few buckets it will be densely full and have many collisions. If a hash map has more buckets it
will be more sparsely populated, there will be less collisions, but there may be a lot of extra empty space.

### Methods


-set()

send the key to the hash() method. ,Once you determine the index of where it should be placed, go to that index,Check if something exists at that index already, 
if it doesn’t, add it with the key/value pair. If something does exist, add the new key/value pair to the data structure within that bucket.

-get()

The get() method takes in a key, gets the Hash, and goes to the index location specified. 

-has()

The has() method will accept a key, and return a bool on if that key exists inside the hashtable.

-keys()

The keys() method returns a collection (array) of unique hash keys.

-hash()

The hash() method will accept a key as a string, conduct the hash, and then return the index of the array where the key/value should be placed.
