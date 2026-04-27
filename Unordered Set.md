## Initialization:
```
unordered_set<int> mySet;
```


## Methods:

### Count :

Returns 0/1 based on element presence 
if (mySet.count(key) > 0)

## Find :
To check existence, first check if the iterator is at the end. (Note: Unlike maps, there is no mapped value to query, knowing it exists is enough)
if (mySet.find(key) != mySet.end()) {
	// element is present in the set
}

## Insert :

- Adds an element to the set (does nothing if it already exists)

```
mySet.insert(key);
```

## Erase :

- Removes the element from the set by its value

```
mySet.erase(key);
```
## Clear :

- Removes ALL elements from the set at once, making its size 0

```
mySet.clear();
```

## Size :

- Returns the total number of elements currently in the set

```
int n = mySet.size();
```

## Empty :

- Returns true if the set has no elements, false otherwise (faster than checking size() == 0)

```
if (mySet.empty()) {
	// set is empty
}
```

## Iteration :

- Loop through all elements in the set (Note: elements will print in random/unordered sequence)

```
for (int num : mySet) {
	// do something with num
}
```