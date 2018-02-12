#1.新的数据结构 Set#
    const s = new Set();
    
    [2, 3, 5, 4, 5, 2, 2].forEach(x => s.add(x));
    
    for (let i of s) {
      console.log(i);
    }
    // 2 3 5 4

    // 例一
    const set = new Set([1, 2, 3, 4, 4]);
    [...set]
    // [1, 2, 3, 4]
    
    // 例二
    const items = new Set([1, 2, 3, 4, 5, 5, 5, 5]);
    items.size // 5
    
    // 例三
    function divs () {
      return [...document.querySelectorAll('div')];
    }
    
    const set = new Set(divs());
    set.size // 56
    
    // 类似于
    divs().forEach(div => set.add(div));
    set.size // 56