オブジェクトの定義
var hensu = function() {
  //コンストラクタ
}

```
var Member = function (firstName, lastName) {
    var self = this;
    self.firstName = firstName;
    self.lastName = lastName;

    self.showMessage = function () {
      return this.firstName + ' ' + this.lastName;
    };
};

var mem = new Member("wata", "tomo");
console.log(mem.lastName);
console.log(mem.showMessage());
```

コンストラクタでメソッドを定義すると、インスタンス化するたびにコピーするため
メモリを無駄に消費してしまう。メソッドはコンストラクタで定義せずにプロトタイプで定義するのがセオリー。

```
var Member = function (firstName, lastName) {
    var self = this;
    self.firstName = firstName;
    self.lastName = lastName;
};

Member.prototype = {
  showMessage : function() {
    return this.firstName + ' ' + this.lastName
  },
  toString : function() {
    //doSomething
  }
};

var mem = new Member("wata", "tomo");
console.log(mem.lastName);
console.log(mem.showMessage());
```

```
var Area = function(){};

Area.version = '1.0';

Area.triangle = function(base, height) {
  return base * height / 2;
};

console.log(Area.version);
console.log(Area.triangle(5,3));
```

```
var Animal = function (name) {
    this.name = name;
};

Animal.prototype = {
    walk : function () {
        console.log("tokotoko");
    },
    showName : function () {
        console.log('my name is ' + this.name);
    }
};

var Dog = function (name) {
    Animal.call(this, name);
};
Dog.prototype = new Animal(name);
Dog.prototype.balk = function () {
    console.log('wanwan');
}
//TODO これだと walk is not functionとエラーが出る
// Dog.prototype = {
//     balk : function () {
//         console.log('wanwan');
//     }
//
// };

var dog = new Dog('tomo');
dog.walk();
dog.balk();
dog.showName();
```