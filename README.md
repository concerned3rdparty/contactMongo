```scala
val f = FIFO[Char](5) // a FIFO buffer of length 5 and type Char
{ 'a' to 'h'}.map(f.push(_)) // the buffer holds h,g,f,e,d
f.last(2) // returns Array[Char](g, h), i.e., the last 2 elements, order is not guaranteed!!
f.at(0) // returns h, i.e. the latest element
f.at(1) // returns g
f.at(4) // returns d
f.last(4) // returns Array(f, g, h, e)
f.at(5) // returns d
f.at(6) // returns d, since 6 >= FIFO length
f.last(6) // returns Array(f, g, h, d, e)
```
