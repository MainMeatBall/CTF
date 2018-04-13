# texts #65
**Description:**

***ENG***

> The beginning is the end and vice versa.

> The answer is 32 symbols long.

***RU***

> Там, где начало, там же и конец, и наоборот.

> Ответ ровно 32 символа.

Task: e1f09c1089196c1ccc11611c929|c99b162122ccf601bf9920f|ce21999c178ce90e|100fffb100610f696cc10c9|60cc909220919e2fc0c0c9|c202e6909929c1e100|1c00a8217072fc99c8e67|99e29129c96709102f182951e90198fa|0cf0c0fe02e190526c26c91b2a00c5|00909907b11e195016f|8a99ee9028cef608209fe8e1110ee5c09|bf185796cc6708cf09f9ae7c|91fa15292a911209699e09c16f15fc60|206009000299efc0ce699ecb69|029900c102812050a5087c6a66700a82|69f521c9c1c1c90cc9fa0961|1909099900fea99e68eab250606|29ef191100991689122990810e10160|90679ce969050f9a0f2|051698092cbc06901909|caafc92e96c99890c69c2657c9912210b|972f08e712501109c01658|ffb9c0cf2bf8a9cca9901b6c7679bf190|500e9ef29ca69c9ac19967106019f0|a96c29a9c9509c9c99|79f02ccc0ccc259c15c961|019005b07cab9e9ec1092cc055c|908ce9956e266191969210ff6|906559c661ee2ac2c9eb0cf71|eb0901cf112ee9e67ccc78c|f968099e990006119fe9f6099cc|922bb86f9ce0e098e


## Writeup

Actually, I don't have a writeup for this task because here is nothing to explain. The main point is `The beginning is the end and vice versa.`. So we can just see that there are 32 blocks separated by `|` and we should somehow covert different amount of symbols into one. And if you start from the beginning and you will write only a first symbol of each block, you can see that it is the same result as if you start from the end but using the last symbol of each block. 

My personal opinion is that this task is pointless, however it exists. You can use python for extracting the data

```python
str = 'e1f09c1089196c1ccc11611c929|c99b162122ccf601bf9920f|ce21999c178ce90e|100fffb100610f696cc10c9|60cc909220919e2fc0c0c9|c202e6909929c1e100|1c00a8217072fc99c8e67|99e29129c96709102f182951e90198fa|0cf0c0fe02e190526c26c91b2a00c5|00909907b11e195016f|8a99ee9028cef608209fe8e1110ee5c09|bf185796cc6708cf09f9ae7c|91fa15292a911209699e09c16f15fc60|206009000299efc0ce699ecb69|029900c102812050a5087c6a66700a82|69f521c9c1c1c90cc9fa0961|1909099900fea99e68eab250606|29ef191100991689122990810e10160|90679ce969050f9a0f2|051698092cbc06901909|caafc92e96c99890c69c2657c9912210b|972f08e712501109c01658|ffb9c0cf2bf8a9cca9901b6c7679bf190|500e9ef29ca69c9ac19967106019f0|a96c29a9c9509c9c99|79f02ccc0ccc259c15c961|019005b07cab9e9ec1092cc055c|908ce9956e266191969210ff6|906559c661ee2ac2c9eb0cf71|eb0901cf112ee9e67ccc78c|f968099e990006119fe9f6099cc|922bb86f9ce0e098e'.split('|')
flag = ''
for i in str:
    s += i[0]
print(s)
```

Flag: `ecc16c19008b92061290c9f5a7099ef9`

### Link

https://freehackquest.com/?quest=65
