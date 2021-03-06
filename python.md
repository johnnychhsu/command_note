### Using jupyter lab on remote server
First start up the jupyter server on remote machine
```
jupyter lab --port=9000 --no-browser
```
Then run this on local machine 
```
ssh -N -f -L [local_port]:localhost:[remote_port] [User]@remote_machine
```

#### Add virtualenv in Jupyter lab
First source your virtualenv, then install ipykernel
```
pip install ipykernel
```
Then install your virtualenv into Ipykernel
```
python -m ipykernel install --user --name=<virtualenv_name>
```
Run jupyter lab, change the kernel.

#### Convert Ipython notebook to py file
jupyter nbconvert --to script file.ipynb

### Pyenv and Pipenv
Reference : https://hackernoon.com/reaching-python-development-nirvana-bb5692adf30c

### Python Tip

#### Miscellaneous
**Built-In Function**
1. `ord(str)` : take str as input, output its ascii or unicode.
2. `chr(int)` : take number as input, output its str.
3. `callable(arg)` : If arg is callable (such as function), return True, else False. 
4. `getattr(obj, name)(args)` : Get the attribute `name` (obj's function or attribute). we can use this to pass an obj and call its function in other place.

**Tips**  
Tuple is faster than list, because it is not mutable.

#### Sort
In Python2.x, we can use `cmp` as our comparison function for sorting. In Python3.x, there is no `cmp` argument. We can use cmp_to_keym to specify our comparison function as input for `key` argument.
  
```python
from functools import cmp_to_key
a=[5,3,4,2,7]
a=list(map(str, a))
sorted(a, key=cmp_to_key(lambda x, y: x+y > x-y), reverse=True)
```

#### collections
A useful built-in library. Helps in lots of tasks.
1. deque
    1. pop()
    2. popleft()
    3. extend(iterable)
    4. extendleft(iterable)
    5. append()
    6. appendleft()
2. namedtuple
    1. `Identity = namedtuple('Identity', 'name, age, gender')`. But this is slower than dict.
3. ChainMap
    1. `dict = ChainMap(dict_1, dict_2, doct_3)`. Helps to chain dict together.
4. Counter
    1. `Counter(list())`. We can initialize Counter with a list, also we can update the list later.
5. OrderedDict
6. defaultdict
    1. `defaultdict(func)`. If no related key in the dict, return the func we define for the initialization.

#### Min for dictionary
```python
a = {5:1, 6:2, 7:3}

# will print 5
min(a, key=a.get)

a = {'a':1, 'b':2}

# will print 'a'
min(a. key=a.get)
```

#### Bisect
```python
def grade(score,breakpoints=[60, 70, 80, 90], grades='FDCBA'):
    i = bisect.bisect(breakpoints, score)
    return grades[i]

print [grade(score) for score in [33, 99, 77, 70, 89, 90, 100]]
```

#### list.insert()
```python
a = []
a.insert(0,4)
# a = [4]
a.insert(8,55)
# a = [4,55]
# Even though the index is out off range, insert will put it at the last position
```
#### heapq
Heapq will take item in list order by index as the priority.
```python
import heapq
a = []
heapq.heappush(a, [[1,'sss',
                    2, 'ddd'
                    3, 'fff']])
# will pop out [1, 'sss']
heappop(a)
```
To avoid the same priority, we can add the push order index as an item in the middle. If there are items that have the same priority, the push order can be the judge.

#### Scope
If we want to access a variable like this : 
```python
def f(): 
    print(s)
    s = "I love London!"
    print(s) 

s = "I love Paris!" 
f()
```
This will lead to `UnboundLocalError: local variable 's' referenced before assignment`. Because this first time we use `s` in `f()`, we try to treat `s` as global variable. Then we want to assign a value to `s`, this causes ambiguity, thus python will report an error.

#### divmod
This is a built-in function.
```python
a, b = divmod(6,4)
# a = 1, b = 2
```