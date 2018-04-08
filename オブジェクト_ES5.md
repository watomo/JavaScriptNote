
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