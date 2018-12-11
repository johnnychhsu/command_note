## Command note
Here I save some useful command for me, help to improve my working efficiency.

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


### Python Tip

#### Miscellaneous
ord() : take str as input, output its ascii.
chr() : take number as input, output its str.
  
Tuple is faster than list.

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
    3. extend()
    4. extendleft()
2. namedtuple
    1. `Identity = namedtuple('Identity', 'name, age, gender')`. But this is slower than dict.
3. ChainMap
    1. `dict = ChainMap(dict_1, dict_2, doct_3)`. Helps to chain dict together.
4. Counter
    1. `Counter(list())`. We can initialize Counter with a list, also we can update the list later.
5. OrderedDict
6. defaultdict
    1. `defaultdict(func)`. If no related key in the dict, return the func we define for the initialization.

### Mysqlsh Note
When in mysqlsh, first need to connect to the SQL server.
```
\connect [user]@[ip_address]
```
In local, it's like
```
\c root@localhost
```
Then if want to run .sql file, run :
```
\. file.sql ;
```

### Git Alias Command
This is useful. Save time.
```
git config --global alias.st status
git config --global alias.ci commit
```

### personal .vimrc
Save my .vimrc with plugin.
After add plugin into .vimrc, type `:PluginInstall`.

Here is some plugin note:
1. Nerdtree : 
    1. map Nerdtree into Ctrl+O. Type Ctrl+O in Vim to view file tree.
    2. `:t` to open the file in a new tab.
2. surround : 
    If `"Hello World"`,
    1. Type directly in the editor `cs"'` to change the surrounding `"` into `'`. Change the symbol accordingly. 
    2. Type directly in the editor `ds"` to delete the surrounding `"`. 
    3. Suppose now is `Hello World`, type `ysiw]` (iw is a text subject) cursor on Hello, it becomes `[Hello] World`.

### Pyenv and Pipenv
Reference : https://hackernoon.com/reaching-python-development-nirvana-bb5692adf30c

### Markdown cheatsheet
#### Code block
\```[code name]
\```
