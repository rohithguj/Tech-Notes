
## Initialization:

```
vector<int> v = {1, 2, 3, 4};

vector<int> v(5); // Default with 0 size 5

vector<int> v(5); // Default val 10 size 5

```

## Methods:

### size:

- To find the size of array

```
int length = nums.size();
```


### empty :

- Returns bool 

```
if (nums.empty()) { ... }
```

### access element :

```
int first = nums[0];

int first = nums.at(0); // Include boundry check returns out of bounds

int front = nums.front(); // Returns first element

int back = nums.back(); // Returns last element


```


### push_back()

- Insert element in last


### pop_back()

- Remove element in last


### clear()

- Remove element in last

### insert()

- Inserts at an index

```
nums.insert(nums.begin() + 1, 99); // Inserts 99 at index 1
```


### erase()

- removes element at a certain index

```
nums.erase(nums.begin() + 2); // Removes the element at index 2
```


### begin()

- returns the start of the vector