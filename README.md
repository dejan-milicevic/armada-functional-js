# armada-functional-js
Armada: Functional JS

```
var bool = true ? 'Yes' : 'No';
console.log(bool)
var TRUE = a => b => a
console.log(TRUE("YES")("NO"))
var FALSE = a => b => b
console.log(FALSE("YES")("NO"))
var NOT = f => a => b => f(b)(a)
console.log(NOT(FALSE)("YES")("NO"))
console.log(NOT(TRUE)("YES")("NO"))
var ZERO = f => x => x
var ONE = f => x => f(x)
var TWO = f => x => f(f(x))
var THREE = f => x => f(f(f(x)))
var doSomething = () => console.log('SOMETHING')
doSomething()
var doSomethingTwice = TWO(doSomething)
doSomethingTwice()
var toNum = (numFn) => {
    let count = 0;
    numFn(() => count++)();
    console.log(count);
}
toNum(ONE)
toNum(TWO)
toNum(THREE)
var SUM = a => b
var SUM = a => b => b(SUCCESSOR)(a)
var SUCCESSOR = n => n
toNum(SUCCESSOR(TWO))
var SUCCESSOR = n => f => x => f(n(f)(x))
var FOUR = SUCCESSOR(THREE)
toNum(FOUR)
var FIVE = SUM(TWO)(THREE)
toNum(FIVE)
var SIX = SUM(TWO)(FOUR)
toNum(SIX)
var MULT = a => b => f => a(b(f))
var EIGHT = MULT(TWO)(FOUR)
toNum(EIGHT)
var EXP = a => b => b(a)
var NINE = EXP(THREE)(TWO)
toNum(NINE)
var SUB = a => b => b(PREDECESSOR)(a)
var PAIR = a => b => f => f(a)(b)
var FIRST = TRUE
var SECOND = FALSE
var box = PAIR("serbia")("brazil")
console.log(box(FIRST))
console.log(box(SECOND))
var INCREMENT_PAIR = p => PAIR(p(SECOND))(SUCCESSOR(p(SECOND)))
var ZERO_ZERO = PAIR(ZERO)(ZERO)
var result = INCREMENT_PAIR(ZERO_ZERO)
toNum(result(FIRST))
toNum(result(SECOND))
var result = TWO(INCREMENT_PAIR(ZERO_ZERO))
toNum(result(SECOND))
toNum(result(FIRST))
toNum(result(SECOND))
var result = TWO(INCREMENT_PAIR)(ZERO_ZERO)
toNum(result(FIRST))
toNum(result(SECOND))
var PREDECESSOR = n => n(INCREMENT_PAIR)(ZERO_ZERO)
var PREDECESSOR = n => n(INCREMENT_PAIR)(ZERO_ZERO)(FIRST)
var SEVEN = PREDECESSOR(EIGHT)
toNum(SEVEN)
var SUB = a => b => b(PREDECESSOR)(a)
toNum(SUB(FIVE)(TWO))
toNum(SUB(SEVEN)(ONE))
toNum(SUB(SEVEN)(THREE))
toNum(SUB(FIVE)(ONE))
toNum(SUB(FIVE)(ONE))
var IF = i => i
var AND = a => b => a(b)(a)
var OR = a => b => a(a)(b)
console.log(AND(TRUE)(TRUE)('YES')('NO'))
console.log(AND(TRUE)(FALSE)('YES')('NO'))
console.log(AND(FALSE)(FALSE)('YES')('NO'))
console.log(AND(FALSE)(TRUE)('YES')('NO'))
console.log(AND(TRUE)(TRUE)('YES')('NO'))
console.log(OR(TRUE)(TRUE)('YES')('NO'))
console.log(OR(FALSE)(TRUE)('YES')('NO'))
console.log(OR(FALSE)(FALSE)('YES')('NO'))
console.log(OR(FALSE)(TRUE)('YES')('NO'))
var IS_ZERO = a => a(TRUE(FALSE))(TRUE)
console.log(IS_ZERO(ZERO)('YES')('NO'))
console.log(IS_ZERO(ONE)('YES')('NO'))
console.log(IS_ZERO(TWO)('YES')('NO'))
var LEQ = a => b => IS_ZERO(SUB(a)(b))
console.log(LEQ(TWO)(TWO)('YES')('NO'))
console.log(LEQ(ONE)(TWO)('YES')('NO'))
console.log(LEQ(ONE)(TWO)('YES')('NO'))
console.log(LEQ(ONE)(THREE)('YES')('NO'))
console.log(LEQ(THREE)(TWO)('YES')('NO'))
var EQ = a => b => AND(LEQ(a)(b))(LEQ(b)(a))
console.log(EQ(ONE)(THREE)('YES')('NO'))
console.log(EQ(THREE)(THREE)('YES')('NO'))
console.log(EQ(THREE)(ONE)('YES')('NO'))
var GT = a => b => NOT(LEQ(a)(b))
console.log(GT(ONE)(THREE)('YES')('NO'))
console.log(GT(ONE)(ONE)('YES')('NO'))
console.log(GT(THREE)(ONE)('YES')('NO'))
var foo = a => b =>
    IF(EQ(a)(b))(
        SUM(MULT(a)(TWO))(b)
    )(
        IF(GT(a)(b))(
            SUB(a)(b)
        )(
            MULT(a)(b)
        )
    )
toNum(foo(FOUR)(THREE))
var IBIS = a => a
var KESTREL = a => b => a
var KITE = a => b => b
var BLUEBIRD = f => g => x => f(g(x))
var CARDINAL = f => a => b => f(b)(a)
var VIREO = a => b => f => f(a)(b)
var THRUSH = a => f => f(a)
var STARLING = f => g => x => f(x)(g(x))

```
