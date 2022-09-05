### JavaScript RxJS
Reactive Extensions Library for JavaScript

**Async/await ?**

RxJS is a library for reactive programming using Observables, to make it easier to compose asynchronous or callback-based code. This project is a rewrite of Reactive-Extensions/RxJS with better performance, better modularity, better debuggable call stacks, while staying mostly backwards compatible, with some breaking changes that reduce the API surface

**Interval**

Creates an Observable that emits sequential numbers every specified interval of time


```node 
	interval$:any;

    this.interval$=interval(1000).pipe(map( r => r+10)).subscribe(x=>{
      console.log(x);
    });

    let index=0;

    setInterval(()=>{
      index++;
      console.log(index);
    },1000);
```

**Output**

```node
10
11
12
...
```


**Reference**

[rxjs](https://rxjs.dev/api/index/function/interval),