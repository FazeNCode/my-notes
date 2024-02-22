<h3> How to convert a Decimal number to a Binary </h3>

In order to convert a decimal number to binary, we must divide the decimal number by 2, and note down the remainder once it's divided. 
For example, to convert the decimal number "25" we would divide 25 by 2, which gives us 12.5. 
We then round down the number to 12 meaning we have 1 remainder. R = 1
Next we divide "12" with 2 which gives us 6, here we do not have any remaining, so we can put a R = 0
Next we can divide 6/2 which gives us 3 with 0 remainder  R = 0
Next we can divide 3/2 which gives us 1.5, we can round it down to 1, which gives us R = 1
Next we can divide 1/2 which gives us 0.5, which we can round down to 0, which gives us R = 1


25/2 = 12.5    R=1
12/2 = 6       R=0
6/2 =  3       R=0
3/2 = 1.5      R=1
1/2 = 0.5      R=1

Now to compress the decimal to binary, we will count from bottom to top, for example the example above will transpire

```
11001
```
It is best practice to always round the bits to either 4,8,12 etc... For example in the result above we have 5 bits in total, to round up we can add an additional 0's in front

```
00011001
```

