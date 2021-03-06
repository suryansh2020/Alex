# Alex
![alt tag](http://thesmashable.com/wp-content/uploads/2012/06/Madagascar-3-movie-2012-Alex-The-Lion-HD-Wallpaper-31.jpg)
A Command Line Interface to execute test cases embedded within a python code.
Its as simple as 123, just embed the code in the given format and do
`$ alex <filename>.py`

# Installation
`$ python setup.py install`

# Requirements
- `python 2.7.x`
- `docopt>=1.6.2`

# Usage
The file should contain test cases in the format:

- The inputs for the file should be in the format
```
"""I
your input should go here
"""
```
- The outputs for the file should be in the format
```
"""O
your expected output should go in here.
"""
```

The above 2 comments can be anywhere in the file. If you run only with inputs, you will just recieve the output.
Also you can have multiple inputs/outputs but length of outputs(if any) should have the same length as inputs,
input-output should have same order.

And then execute

`$ alex <file-name>`

# Example
The following is an example file for demonstration:
The below file is `test.py` which is a python solution to [this problem on Hackerrank](https://www.hackerrank.com/challenges/solve-me-second).
```
def solveMeSecond(a,b):
   return a+b

n = int(raw_input())

for i in range(0,n):
    a, b = raw_input().split()
    a,b = int(a),int(b)
    res = solveMeSecond(a,b)
    print res
    
"""I
2
2 3
3 7
"""

"""O
5
10
"""
```
Now execute
```
$ alex test.py
Alex is working on  test.py

YOUR OUTPUT
===========
5
10

EXPECTED OUTPUT
===============
5
10

PASS/FAIL (of 1 testcases)
=========
TESTCASE 1 PASS
```
You can aslo have multiple testcases like this:
```
def solveMeSecond(a,b):
   return a+b

n = int(raw_input())

for i in range(0,n):
    a, b = raw_input().split()
    a,b = int(a),int(b)
    res = solveMeSecond(a,b)
    print res

"""I
2
2 3
3 7
"""

"""O
5
10
"""

"""I
3
1 2
3 7
4 5
"""

"""O
3
10
9
"""
```
If you run:
```
$ alex test.py
```
output :
```
Alex is working on  test.py

YOUR OUTPUT
===========
5
10

3
10
9

EXPECTED OUTPUT
===============
5
10

3
10
9

PASS/FAIL (of 2 testcases)
=========
TESTCASE 1 PASS
TESTCASE 2 PASS
```

#Contributors

@kaushik94
@brennan-v-
