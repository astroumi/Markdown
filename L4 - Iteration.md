# Iteration
**Review: an iterable object is an object we can traverse through (such as a string, list, dictionary, or set)**

```python
class Deck:
	#… Code …
	def __iter__(self):
		return self

	def __next__(self):
		self.__index += 1
		if self.__index == len(self.__cards):
			self.__index = -1 # index reset
			raise StopIteration
		else:	
			return self.__cards[self.__index]
```

### How to make an instance of a class iterable

**`__iter__()`**
Allows our object to be iterable, when invoked upon (ex. By a for loop), it will call the method. Commonly just returns it self.

**`__next__()`**
Allows us to get to the next value when iterating:
Common Practice: 
set an index attribute to -1 increment the index attribute by 1 until self.__index is equal to length of sequence when the end is reached, raise `StopIteration`

### Indexing and Slicing
Too complicated for now