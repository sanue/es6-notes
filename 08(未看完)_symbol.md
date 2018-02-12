## 1.Symbol 值不能与其他类型的值进行运算，会报错，但Symbol 值可以显式转为字符串。布尔值。 ##

    let sym = Symbol('My symbol');
    
    String(sym) // 'Symbol(My symbol)'
    sym.toString() // 'Symbol(My symbol)'
   
     //布尔值
    let sym = Symbol();
    Boolean(sym) // true
    !sym  // false
    
    if (sym) {
      // ...
    }
    
    Number(sym) // TypeError
    sym + 2 // TypeError