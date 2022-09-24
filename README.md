# javascript-cheatsheet

Creating Observable using javascript

```sh
class Observable {
    constructor(functionThatTakesObserver){
      this._functionThatTakesObserver = functionThatTakesObserver;
    }

    subscribe(observer) {
      return this._functionThatTakesObserver(observer)
    }
}
let myObservable = new Observable(observer => {
  setTimeout(() => {
    observer.next("got data!")
    observer.complete()
  }, 1000)
})

let myObserver = {
  next(data) {
    console.log(data)
  },
  error(e) {
    console.log(e)
  },
  complete() {
    console.log("request complete")
  }
}

myObservable.subscribe(myObserver)

```
