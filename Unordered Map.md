
## Initialization:

```
unordered_map<int, int> myMap;
```


## Methods:

### Count :

- Returns 0/1 based on element presence 

```
if (myMap.count(key) > 0)
```

### Find :

- To find the index first check if iterator is at the end if yes then query the values like a vector

```
if (myMap.find(key) != myMap.end()) {
	int val = map[key]
}
```

