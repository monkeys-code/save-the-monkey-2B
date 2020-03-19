7회차 스터디
2020.3.16

## Round 1
링크드 리스트 add, get, toString, size and isEmpty 구현

#### 고은정
```javascript
class ListNode {
  constructor(val = Number.MIN_SAFE_INTEGER, next = null) {
    this.val = val; // number
    this.next = next; // ListNode
  }
}

class List {
  constructor() {
    this.head = null; // ListNode
  }

  addHead(val) {
    const tempNode = new ListNode(val, this.head);
    this.head = tempNode;
  }

  addTail(val) {
    const newNode = new ListNode(val, null);
    let curNode = this.head;
    while (curNode.next) {
      curNode = curNode.next;
    }
    curNode.next = newNode;
    return newNode.val;
  }

  getNode(index) {
    let curNode = this.head;
    for (let i = 0; i <= index; i++) {
      if (i === 0) {
        curNode = this.head;
      } else {
        curNode = curNode.next;
      }
    }
    return curNode;
  }

  getValue(index) {
    const targetNode = this.getNode(index);
    return targetNode.val;
  }

  isEmpty() {
    return this.head === null;
  }

  size() {
    let length = 0;
    let curNode = this.head;
    while (curNode !== null) {
      ++length;
      curNode = curNode.next;
    }
    return length;
  }
}

export default List;
```

#### 김지훈
```javascript
class ListNode {
  constructor(val = Number.MIN_SAFE_INTEGER, next = null) {
    this.val = val;   // number
    this.next = next; // ListNode
  }
}

class List {
  constructor() {
    this.head = null; // ListNode
  }

  addHead(val) { // number
    const tmpHead = this.head;
    this.head = new ListNode(val, tmpHead);
  }

  addTail(val) {
      let current = this.head;
      while(current.next) {
          current = current.next;
      }
      current.next = new ListNode(val)
  }

  getNode(index) {
      let current = this.head;
      for (let i = 0; i < index; i++) {
          current = current.next;
      }
      return current;
  }

  getValue(index) {
      return this.getNode(index).val;
  }

  isEmpty() {
      if (this.head != null) {
          return false;
      } else {
          return true;
      }
  }

  size() {
      let size = 0;
      let current = this.head;
      while(current) {
          current = current.next;
          size++;

      }
      return size;
  }
}


```

#### 이소은
```javascript

class ListNode {
  constructor(val = Number.MIN_SAFE_INTEGER, next = null) {
    this.val = val; // number
    this.next = next; // ListNode
  }
}

class List {
  constructor() {
    this.head = null; // ListNode
  }

  addHead(val) {
    const new_node = new ListNode(val);
    const head = this.head;
    if (!head) {
      this.head = new_node;
    } else {
      this.head = new_node;
      this.head.next = head;
    }
  }

  addTail(val) {
    const new_tail = new ListNode(val);
    let node = this.head;

    if (!this.head) {
      this.head = new_tail;
    } else {
      while (node.next) {
        node = node.next;
      }
      node.next = new_tail;
    }
  }

  getNode(index) {
    let node = this.head;
    let i = 0;
    let find_node = null;

    while (node) {
      if (i === index) {
        find_node = node;
      }
      node = node.next;
      i++;
    }

    return find_node;
  }

  getValue(index) {
    let node = this.head;
    let i = 0;
    let find_node = null;

    while (node) {
      if (i === index) {
        find_node = node;
      }
      node = node.next;
      i++;
    }
    const { val } = find_node;

    return val;
  }

  isEmpty() {
    if (!this.head) {
      return true;
    }
    return false;
  }

  size() {
    let node = this.head;
    let i = 0;

    while (node) {
      node = node.next;
      i++;
    }

    return i;
  }
}

export default List;

```

#### 서경원
```javascript
class List {
  constructor() {
    this.head = null;
  }

  addHead(val) {
    this.head = new ListNode(val, this.head);
  }

  addTail(val) {
    if (this.isEmpty()) {
      this.head = new ListNode(val);
    } else {
      let node = this.head;
      while (node.next) {
        node = node.next;
      }
      node.next = new ListNode(val);
    }
  }

  getNode(index) {
    let node = this.head;
    for (let i = 0 ; i < index ; i++) {
      node = node.next;
    }
    return node;
  }

  getValue(index) {
    return this.getNode(index).val;
  }

  isEmpty() {
    return this.head === null;
  }

  size() {
    if (this.isEmpty()) {
      return 0;
    }
    let count = 1;
    let node = this.head;
    while (node.next) {
      count++;
      node = node.next;
    }
    return count;
  }
}

class ListNode {
  constructor(val = Number.MIN_SAFE_INTEGER, next = null) {
    this.val = val;
    this.next = next;
  }
}
```

## Round 2
### 링크드 리스트 toString, parse, getMiddle, hasCycle 구현

#### 고은정
```javascript
// Output: "[1,2,3,4,5]"
  toString() {
    if (this.size() === 0) {
      return "[]";
    }

    let string = "[";
    let curNode = this.head;
    string += curNode.val;

    while (curNode.next) {
      curNode = curNode.next;
      string += `,${curNode.val}`;
    }
    string += "]";

    return string;
  }

```

#### 김지훈
```javascript
// Output: "[1,2,3,4,5]"
  toString() {
      const tmpArr = [];

      let current = this.head;
      while(current) {
          tmpArr.push(current.val)
          current = current.next;
      }
      return `[${tmpArr.join(",")}]`;
  }
  
  // static get
  parse(str) {
      const returnObject = new List();
      str.slice(1, str.length -1)
          .split(",")
      .forEach(it => returnObject.addTail(it))

      return returnObject;
  }
  
  getMiddle() {
      const size = this.size;

      if (size == 0) {
          return null;
      } else if (size % 2 == 0) {
          return getValue(size / 2)
      } else {
          return getValue(Math.floor(size / 2))
      }
  }
  
  getMiddleWithOutSize() {
      let slow = this.head;
      let fast = this.head;
      while(slow) {
          slow = slow.next;
          if (fast == null || fast.next == null) {
              break;
          } else {
              fast = fast.next.next;
          }

      }
      return slow.val;
  }
  
  hasCycle() {
      const tmpArr = [];
      let result = false;

      let current = this.head;
      while(current) {
          if (tmpArr.indexOf(current) > -1) {
              result = true;
              break;
          }
          tmpArr.push(current)
          current = current.next;

      }
      return result;
  }

```

#### 이소은
```javascript
 // Output: "[1,2,3,4,5]"
  toString(): string {
    let node = this.head
    let output_str = "["

    if (!this.head) {
      return "[]"
    }

    while(node.next) {
      output_str = `${output_str}${node.val},`
      node = node.next
    }

    output_str = `${output_str}${node.val}]`

    return output_str
  }

  /**
   * @param {string} str
   *   - "[1,2,3,4,5]"
   * @return {List}
   */
  static parse(str) {
    const regex = RegExp("[[(0-9,)]+]");
    if (regex.test(str)) {
      let replaceStr = str.replace("[", "").replace("]", "");
      const list = new List();
      if (replaceStr === "") {
        list.head = null;
      } else {
        replaceStr.split(",").forEach(val => {
          list.addTail(parseInt(val));
        });
      }
      return list;
    }
    return new List();
  }

  /**
   * @return {number} value of ListNode
   */
  getMiddle() {
    const size = this.size()
    if (size === 0) {
      return null
    } else {
      return this.getValue(Math.floor(size / 2))
    }
  }

```

#### 서경원
```javascript
  toString() {
    let str = '';
    for (let node = this.head ; node ; node = node.next) {
      str += ',' + node.val;
    }
    return '[' + str.substring(1) + ']';
  }
  
  getMiddle() {
    if (this.isEmpty()) {
      return null;
    }
    let slower = this.head;
    let faster = this.head;
    while (faster && faster.next) {
      faster = faster.next.next;
      slower = slower.next;
    }
    return slower.val;
  }

  hasCycle() {
    if (this.isEmpty()) {
      return false;
    }
    let slower = this.head;
    let faster = this.head;
    while (faster && faster.next) {
      faster = faster.next.next;
      slower = slower.next;
      if (faster === slower) {
        return true;
      }
    }
    return false;
  }
```

## Round 3
### 링크드 리스트 size없이 getMiddle 구현, reverse 구현
### 고은정
### 서경원
```javascript
  reverse() {
    this.head = this._reverseRecurs(this.head, null);
  }

  _reverseRecurs(curr, prev) {
    if (curr.next) {
      const newHead = this._reverseRecurs(curr.next, curr);
      curr.next = prev;
      return newHead;
    } else {
      curr.next = prev;
      return curr;
    }
  }


  static parse(str) {
    const list = new List();
    const values = str.replace(/[\[\]\s]/g, '').split(',');
    for (let value of values) {
      if (value) {
        list.addTail(parseInt(value));
      }
    }
    return list;
  }
```

### 김지훈
### 이소은
```javascript
reverse() {
  let pre_node = null;
  let node = this.head;

  while (node) {
    let current_node = node.next;
    node.next = pre_node;
    pre_node = node;
    node = current_node;
  }
  return pre_node;
  }

}

```

## Retrospective
### 고은정
### 서경원
### 김지훈
### 이소은
