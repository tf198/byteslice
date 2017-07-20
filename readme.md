## byteslice

Simple way to concat and slice arrays through bytewise encoding and decoding.

```javascript
var b = byteslice(['yes', 1])

bytewise.decode( b.encode(['x']) )
// [['yes', 1], ['x']]
b.decode(b.encode(['x']))
// ['x']

bytewise.decode( b.encode(['x', ['y']]) )
// [['yes', 1], ['x', ['y']]]
b.decode(b.encode(['x', ['y']]))
// ['x', ['y']]

b = b.concat(['no', 0])

bytewise.decode( b.encode(['x']) )
// [['yes', 1], ['no', 0], ['x']]
b.decode(b.encode(['x']))
// ['x']

bytewise.decode( b.encode(['x', ['y']]) )
// [['yes', 1], ['no', 0], ['x', ['y']]]
b.decode(b.encode(['x', ['y']]))
// ['x', ['y']]
```

### compatibility
A change occured in the __bytewise__ encoding somewhere between 0.5 and 1.1 (probably when
it was refactored to bytewise-core).

* __byteslice__#_0.3.x_ => __bytewise__#_1.1.0_
* __byteslice__#_0.2.x_ => __bytewise__#_0.5.0_

Mixing versions of bytewise is not advisable so if you are using an old version of bytewise
ensure you reference the 0.2 branch.
