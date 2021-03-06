# Chapter 2

## 2.1 完成下面的数字转换
1. 0x8F7A93 -> 二进制:
    - 1000 1111 0111 1010 1001 0011
2. 1011 0111 1001 1100 -> 十六进制:
    - 0xB79C
3. 0xC4E5D -> 二进制:
    - 1100 0100 1110 0101 1101
4. 11 0101 1011 0111 1110 0110 -> 十六进制:
    - 0x35B7E6

## 2.2 填写下表中的空白项，给出2的不同次幂的二进制和十六进制表示:
| n |2^n(十进制)|2^n(十六进制)|
|---|----------|------------|
|11 |2048      |       0x800|
|7  |128       |        0x80|
|13 |8192      |      0x2000|
|13 |8192      |      0x2000|
|16 |65536     |     0x10000|
|8  |256       |       0x100|
|5  |32        |        0x20|

## 2.3
|十进制|  二进制  |十六进制|
|-----|---------|-------|
|    0| 00000000|     00|
|   55| 00110011|     33|
|  136| 10001000|     88|
|  243| 11110011|     F3|
|   82| 01010010|     52|
|  172| 10101100|     AC|
|  231| 11100111|     E7|
|  167| 10100111|     A7|
|   62| 00111110|     3E|
|  188| 10111100|     BC|

## 2.4
1. 0x502C + 0x8 = 0x5024
2. 0x502C - 0x30 = 0x4FFC
3. 0x502C + 64 = 0x5090
4. 0x50DA - 0x502C = 0xAE

## 2.5
```cpp
void practice_5() {
    int val = 0x12345678;
    byte_pointer valp = (byte_pointer) &val;
    show_bytes(valp, 1); /* A. */
    show_bytes(valp, 2); /* B. */
    show_bytes(valp, 3); /* C. */
}
```
- A. 小端法：78，大端法：12
- B. 小端法：7856，大端法：1234
- C. 小端法：785634，大端法：123456


## 2.6
```
show_int(3490593) -> 0x00354321
show_float(3490593.0) -> 0x4A550C84
```
A.  
0x00354321 = 0000 0000 0011 0101 0100 0011 0010 0001  
0x4A550C84 = 0100 1010 0101 0101 0000 1100 1000 0100  
B.C.  
00000000001101010100001100100001  
  01001010010101010000110010000100    
偏移2位，有21位重叠，float的二进制前9位不匹配

## 2.7
41 42 43 44 45 46 00

## 2.8
|运算  |结果    |
|-----|--------|
|a    |01101001|
|b    |01010101|
|~a   |10010110|
|~b   |10101010|
|a&b  |01000001|
|a\| b|01111101|
|a^b  |00111100|

## 2.9
- A.  
111 011
110 010
101 001
100 000
- B.
黑/白
- C.  
蓝色 | 红色 = 101 = 红紫色  
红紫色 & 蓝绿色 = 001 = 蓝色  
绿色 ^ 白色 = 111 = 白色

## 2.10
```cpp
void inplace_swap(int *x, int *y) {
    *x = *x ^ *y; /* Step 1 */
    *y = *x ^ *y; /* Step 2 */
    *x = *x ^ *y; /* Step 3 */
}
```
|步骤   | *x|  *y  |
|------|-----|-------|
|   初始|   a|     b|
| 第一步| a^b|     b|
| 第二步| a^b|     a|
| 第三步|  b|     a|

## 2.11
```cpp
int x = 0x98FDECBA
/* A */ 
x | ~0xFF
/* B */
x ^ 0xFF
/* C */
x & ~0xFF
```

## 2.12
```cpp
int bis(int x, int m) {
    int result = x | m;
    return result;
}

int bic(int x, int m) {
    int result = x & m; // 答案是 x & ~m 迷惑
    return result;
}
```

## 2.13
x = 0x66,y = 0x93
|表达式|结果|
|-----|----|
|x & y|  0x02  |
|x \| y|  0xF7   |
|~x \| ~y| 0xFD     |
|x & !y|   0x00  |
|x && y|  0x01   |
|x \|\| y|  0x01   |
|!x \|\| !y|   0x00   |
|x && ~y|  0x01    |

## 2.14
```cpp
!(x ^ y)
```

## 2.15
- 逻辑右移K位：左边补K个0
- 算数右移K位：左边补K个最高有效位

|             x|          x<<3|          x>>2|          x>>2|
|--------------|--------------|--------------|--------------|
| 0xF0 11110000| 10000000 0x80| 00111100 0x3C| 11111100 0xFC|
| 0x0F 00001111| 01111000 0x78| 00000011 0x03| 11000011 0xC3|
| 0xCC 11001100| 01100000 0x60| 00110011 0x33| 11110011 0xF3|
| 0x55 01010101| 10101000 0xA8| 00010101 0x15| 00010101 0x15|

## 2.16
|十六进制|二进制|B2U4|B2T4|
|-|-|-|-|
|A|[1010]|2^3+2^1=10|-2^3+2^1=6|
|0|[0000]|0|0|
|3|[0011]|2^1+2^0=3|2^1+2^0=3|
|8|[1000]|2^3=8|-2^3=-8|
|C|[1100]|2^3+2^2=12|-2^3+2^2=-4|
|F|[1111]|2^3+2^2+2^1+2^0=15|-2^3+2^2+2^1+2^0=-1|

## 2.17
- A.388
- B.8
- C.12
- D.16
- E.4294966932
- F.16
- G.4294966944
- H.4294967056
- I.28
- J.4294967164
- K.24

## 2.18
| x|T2U(x)|
|--|------|
|-8|     8|
|-6|    10|
|-4|    12|
|-1|    15|
| 0|     0|
| 3|     3|

## 2.19
| x|  T2U(x)|
|--|--------|
|-8| 8(16-8)|
|-6|10(16-6)|
|-4|12(16-4)|
|-1|15(16-1)|
| 0|    0(0)|
| 3|    3(3)|

