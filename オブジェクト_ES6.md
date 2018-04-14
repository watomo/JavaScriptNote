ES6クラス構文
```
class Member {
    constructor(firstName, lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }

    getName() {
        return this.lastName + this.firstName;
    }
}

let member = new Member('tomo', 'wata');
console.log(member.getName());
```

```
staticメソッド
class Area {
    static getTriangle(base, height) {
        return base * height /  2;
    }
}
```