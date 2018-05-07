# Your_brain_crash #98
**Description:**

```с
char *ptr = array;

lol         =   --*ptr; 
lool        =   ++*ptr; 
loool       =   --ptr; 
looool      =   ++ptr; 
loooool     =   putchar(*ptr); 
looooool    =   *ptr=getchar(); 
loooooool   =   while (*ptr) { 
looooooool  =   }
```

[Attached file](/FHQ/files/ppc/your_brain_crash.txt)

## Writeup

First of all, you just replace lo..ls with corresponded actions and it is obvious that they are from C language. So, we will save this text to some file like `file.c` and see what we get.

```python
import re

with open('your_brain_crash.txt', 'r') as f:
	text = f.read()
	a = re.findall(r'lo+l', text)

	dic = {'lol': '--*ptr;\n',
	       'lool': '++*ptr;\n',
	       'loool': '--ptr;\n',
	       'looool': '++ptr;\n',
	       'loooool': 'putchar(*ptr);\n',
	       'looooool': '*ptr = getchar();\n',
	       'loooooool': 'while (*ptr) {\n',
	       'looooooool': '}\n'}

	with open('file.c', 'w') as of:
		of.write('char *ptr = malloc(sizeof(char) * 1024);\n')
		for i in a:
		    of.write(dic.get(i))
```

It is obvious that the main function `int main() {}` is missing, so let's add it and to prevent of showing up any warnings, I added some lines before `main()` function. 

```c
#include <stdlib.h>
#include <stdio.h>

#define putchar(c) putc(c, stdout)
```

Then, let's compile it with `gcc file.c -o flag` and run this program. We will get a python script with incorrect registers of some letters. After modifying this script a little bit we will get this.

```python
import zlib, base64

s = "eJzLzC3ILypRqMrJTNJRSEosTjUzUeDlKijKzCtRUI/MLy1yy0lMVwcA/4YMuQ=="
c = base64.b64decode(s)
d = zlib.decompress(c)

exec(d)
```

After running this script using python2, we will get `YourFlag`. That's all.

Flag: `YourFlag`

### Link

https://freehackquest.com/?quest=98
