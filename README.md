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

## Language
Python 3.5.2

## Files submitted
* **hashmap.py** - contains the class of hashmap with required functions.
* **hashmapTests.py** - contains 14 test cases for testing the hashmap functions.

## Run the tests

To run the tests, Python 3 is required to be installed. Run the following command for testing

`$ python hashmapTests.py`

Sample output

```r
..............
----------------------------------------------------------------------
Ran 14 tests in 0.002s

OK
```

## Output

The results of the unit tests will be displayed, which are used to test the set(), get(), delete() and load().

## Hashing Function

The implementation uses Python's native [hash() function](https://docs.python.org/2/library/functions.html#hash)

## Implementation

The fixed size hash map was created using a list of tuples. Each entry's 
key is hashed and stored at that location of the list.

## Collision Resolution

In this implementation, [Linear Probing](https://en.wikipedia.org/wiki/Linear_probing) is used for collision resolution.
If two different keys have the same hash value, the new entry will be
placed at the next free hash value location. If an entry with an already
existing key is inputted, the value for that key will be replaced with the new entry value.

## Algorithm Complexity

* Without collision
	* Best/Average/Worse Case - set, get, delete - O(1)
* With collision
	* Worse Case - set, get, delete  - O(N)

## Author
Zibo Zhao
