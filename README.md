# 2016 KPCB Fellowship Challenge Problem - Hashmap
Using only primitive types, implement a fixed-size hashmap that associates string keys with arbitrary data object references (don't need to copy the object). 

## Hashmap functions
Providing the following functions:
* **constructor(size)**: return an instance of the class with pre-allocated space for the given number of objects.
* **boolean set(key, value)**: stores the given key/value pair in the hash map. Returns a boolean value indicating success / failure of the operation.
* **get(key)**: return the value associated with the given key, or null if no value is set.
* **delete(key)**: delete the value associated with the given key, returning the value on success or null if the key has no value.
* **float load()**: return a float value representing the load factor (`(items in hash map)/(size of hash map)`) of the data structure. Since the size of the dat structure is fixed, this should never be greater than 1.

The implementation applies Python's a built-in hashing function for strings, `__hash__`. 

**Collision resolution**：if input an entry with an already existing key, the value assocaited with the key will be overwritten by the new entry value.

## Language
Python 3.5.2

## Files submitted
* **hashmap.py** - contains the class of hashmap with required functions.
* **hashmapTests.py** - contains 14 test cases for testing the hashmap functions.

## Run the tests
To use the hashmap class in your code, `from hashmap import Hashmap`.
To run the tests, Python 3 is required to be installed. Run the following command for testing

`$ cd hashmap_KPCB/`
`$ python hashmapTests.py`

Sample output

```
..............
----------------------------------------------------------------------
Ran 14 tests in 0.002s

OK
```

## Complexity
For a fixed size hashmap that can contain up to size items, create a number of buckets which is the smallest power of two that is bigger than size. This minimizes collisions while also optimizing for memory usage. Then for **best/average/worse** cases, it is O(1) for set, get, and delete.

## Author
Zibo Zhao
