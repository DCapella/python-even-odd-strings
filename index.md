# Python Review of Loops and Strings
#### [HackerRank](www.hackerrank.com)

## Problem

> Given a string, S, of length N that is indexed from 0 to N-1, print its even-indexed and odd-indexed characters as 2 space-separated strings on a single line (see the Sample below for more detail).

## Thought Process

```python
# Grab file input as items
# Call function review with parameter items
# In function review, take parameter called items
# Loop through items as item
  # Try if item is int
  # Except run body
    # Remove whitespace
    # Declare empty lists for even and odd
    # Loop through items as letter with index (enumerate)
      # Based on index, append to even or odd
    # Display '{even joined} {odd joined}'
```

## Code

```python
# Grab file input as items
items = fileinput.input()

# Call function review with parameter items
review(items)

# In function review, take parameter called items
def review(items):

# Loop through items as item
for item in items:

  # Try if item is int
  try:
      int(item)
  
  # Except run body
  except:
  
    # Remove whitespace
    item = item.strip()
    
    # Declare empty lists for even and odd
    even, odd = [], []
    
    # Loop through items as letter with index (enumerate)
    for i, letter in enumerate(item):
    
      # Based on index, append to even or odd
      even.append(letter) if i % 2 == 0 else odd.append(letter)
      
    # Display '{even joined} {odd joined}'
    print(f'{"".join(even)} {"".join(odd)}')
    
```

## Final Code

#### With Documentation

```python
# Enter your code here. Read input from STDIN. Print output to STDOUT

import fileinput

def review(items):
  """Displays even and odd letters spaced apart.
  
  Parameter
  ----------
  items: list
    Can be fileinput object.

  Returns
  -------
  None:
    Will print strings, but return nothing.

  Notes
  -----
  * This function will print strings instead of returning anything.
  * It it will not print any newlines, tabs, etc.

  """
  for item in items:
    try:
      int(item)
    except:
      item = item.strip()
      even, odd = [], []
      for i, letter in enumerate(item):
        even.append(letter) if i % 2 == 0 else odd.append(letter)

      print(f'{"".join(even)} {"".join(odd)}')

items = fileinput.input()
review(items)
```

# Conclusion
Even as simple as this problem was, it took me some time to remember best practices such as try-except or that you can not splice an object (i.e. file input object).
As usual, was definitely fun solving it and talking about it.
