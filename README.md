# Hue

![Hue Logo](https://i.imgur.com/coACsyQ.png)

Hue provides a minimal and powerful interface to print colored text and labels in the terminal.\
There are no external dependencies and Hue works with Python 2 as well as Python 3.

## Supported Stuff

Following styles are supported

![Hue Styles](https://i.imgur.com/899ZtQy.png)

Following colors are supported

![Hue Colors](https://i.imgur.com/9tWvPkD.png)

Following labels are supported

![Hue Labels](https://i.imgur.com/dpJxqT2.png)

### Installation
You can install `hue` with **pip** as follows:
```
pip install huepy
```
or with **easy_install**:
```
easy_install huepy
```

### Usage
First of all, import everything that Hue has to offer as follows:

```python
from huepy import *
```

Printing colored text is as simple as doing

```python
print red('This string is red')
```

Easy right?
But what if you want to print italic text?
You can simply do this

```python
print italic('This string is in italic')
```

You can also combine styles and colors

```python
print bold(red('This string is bold and red'))
```

Output:
![Output Examples](https://i.imgur.com/Lo7ZyHq.png)

And what is the use of those labels?\
I have been using these labels in projects as a minimal output schema.\
If some error occured in your program or something else bad happened you don't need to print the whole line in red. With hue, you can simply do this

```python
print bad('An error occured.')
```

Take a look at the output of all the labels
![Label Examples](https://i.imgur.com/zJ7ZgUi.png)

#### List of all colors

```python
white, grey, black, green, lightgreen, cyan, lightcyan, red, lightred,
blue, lightblue, purple, light purple, orange, yellow
```

#### List of all styles

```python
bold, bg, under, strike, italic
```

#### List of all labels

```python
info, que, run, bad, good
```

### Windows 10

**Note:** Windows 10 do support ANSI escape sequences, so the colors will be printed in command prompt if you enable them as follows
In other versions of Windows, they won't be supported (hue_enable_windows_support returns False in that case).

```python
from huepy import *

# Has hue_ since common use is from huepy import *
if not hue_enable_windows_support():
    # Disables ANSI codes if the prompt doesn't support it
    hue_disable()

print(red("a"), blue("b"))
```

Since sometimes the test is negative for some prompts (for example PyCharm Terminal), you may choose to only support Windows prompts that support it
and don't disable the ansi codes

```python
from huepy import *
hue_enable_windows_support()

print(red("a"), blue("b"))
```

### Contribution

The only thing I think **Hue** needs is windows support which I can't add atm because I have no windows machine and made since people were asking for it so its a quick one. So if you can start a pull request for windows support that would be great. Additional colors and labels will be appreciated too.
