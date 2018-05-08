# Some_weird_code #99
**Description:**

***ENG***
> Please, try to fix this [weird code](/FHQ/files/ppc/some_weird_code.txt).

---

***RU***
> Пожалуйста, попытайтесь исправить этот [странный код](/FHQ/files/ppc/some_weird_code.txt).

## Writeup

So, in this file we see some code on perl language. I have no idea how to code on perl, so maybe some of my mistakes are not mistakes at all.

```perl
sub main() {
    my $j = '''@b(defgh|jk3m#9pqr$+uvwxy2''';
    for (int $i=0;$i<32;++$i) {
        print (grep{/\S/}split('\W|',$j))[$i%(split('',$j))[11]+$i%(split('',$j))[25]*$i%19];
    }
    print "\n";
    return 0;
}
main() unless caller;
```

The first mistake I saw was `argc, argv` arguments in main function. Then I removed extra single-quotes in `$j` variable. After that I removed `int` in **for loop**.  Then there were missing braces after `print` function. That's pretty much it. The working code looks like

```perl
sub main() {
    $j = '@b(defgh|jk3m#9pqr$+uvwxy2';
    for ($i=0;$i<32;++$i) {
        print ((grep{/\S/}split('\W|',$j))[$i%(split('',$j))[11]+$i%(split('',$j))[25]*$i%19]);
    }
    print "\n";
}
main() unless caller;
```
And after running it gives us `beefdkb3emdrbuevd2bdeedjbke3dqbr`. 

Flag: `beefdkb3emdrbuevd2bdeedjbke3dqbr`

### Link

https://freehackquest.com/?quest=99
