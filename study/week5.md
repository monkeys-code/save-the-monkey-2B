5회차 스터디
2020.2.29

코로나 위기를 뚫고..

## Round 1
### // 여러가지 타입을 받을 수 있는 array에서, 유니크한 값만 찾아서 배열로 반환하기
[1, 2, 3, 2, 3, 5] => [ 1, 2, 3, 5]
["1", 1, {foo: "bar"}, {foo: "foo"}] => ["1", 1, {foo: "bar"}, {foo: "foo"}]

#### 고은정
```javascript
function solveBySet(input) {
  const set = new Set(input);
  const result = [];
  for (let v of set) {
    result.push(v);  
  }
  return result;
}
```

#### 김지훈
```javascript
function sol1 (arr) {
    return arr.filter((it, idx, self) => self.indexOf(it) == idx)
}

```

#### 이소은
```
```

#### 서경원
```javascript

function solveBySet(input) {
  const set = new Set(input);
  const result = [];
  for (let v of set) {
    result.push(v);  
  }
  return result;
}

```

## Round 2
### Find all files beneath path with file name suffix.

Note that a path may contain further subdirectories
and those subdirectories may also contain further subdirectories.

There are no limit to the depth of the subdirectories can be.

#### 고은정
```javascript
let res = [];
const findFiles = function(suffix, path) {
  const files = fs.readdirSync(path); // 디렉토리를 읽어온다

  files.forEach(file => {
    const subPath = `${path}/${file}`;
    const fileStat = fs.statSync(subPath);
    if (fileStat.isDirectory()) {
      findFiles(suffix, subPath);
    } else {
      const idx = file.indexOf(suffix);
      const sub = file.substring(idx, file.length);

      if (sub === suffix) {
        res.push(`${path}/${file}`);
      }
    }
  });
  return res;
};
```

#### 김지훈
```javascript
const fs = require('fs');

async function dir(path, suffix) {
    return new Promise((resolve, reject) => {
        fs.readdir(path, {withFileTypes: true}, function(err, files) {
            const arr = [];

            arr.push(
                files.filter(it => it.name.endsWith(suffix))
            );

            files.forEach(it => {
                if(it.isDirectory()) {
                    arr.push(dir("./" + path + "/" + it.name, suffix))
                }
            });

            const list = Promise.all(arr);
            resolve(list);

        })
    })

}

(async () => {
    console.log((await dir("./testdir", ".c"))
        .flat(10) // 여기는 무시해주세여
        .map(it => it.name)
    )
})()
```

#### 이소은
```
```

#### 서경원
```java
public List<String> findFiles(String suffix, String path) {
      List<String> results = new LinkedList<>();
      findFiles(suffix, path, results);
      return results;
  }

  public void findFiles(String suffix, String path, List<String> results) {
      if (path.endsWith(suffix)) {
          results.add(path);
      }
      File file = new File(path);
      if (file.isDirectory()) {
          for (File subFile : file.listFiles()) {
              findFiles(suffix, subFile.getPath(), results);
          }
      }
  }
```

## Retrospective
### 고은정
### 서경원
### 김지훈
### 이소은
