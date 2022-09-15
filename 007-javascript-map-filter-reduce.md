### JavaScript Map/Filter/Reduce
JavaScript Map/Filter/Reduce


**Map/Filter/Reduce ?**

Map, reduce, and filter are all array methods in JavaScript. Each one will iterate over an array and perform a transformation or computation. Each will return a new array based on the result of the function. In this article, you will learn why and how to use each one.

**For**

```node 
    const tasks = [
  {
    'name'     : 'Write for Learning',
    'duration' : 120
  },
  {
    'name'     : 'Work out',
    'duration' : 60
  },
  {
    'name'     : 'Movie',
    'duration' : 60
  }
];
const task_names = [];
for (let i = 0; i < tasks.length; i +=1){
    task_names.push(tasks[i].name)
}
console.log(task_names)
```

**Output**

```node
0: "Write for Learning"
1: "Work out"
2: "Movie"
```

**forEach**

```node 
const task_names = [];
  
tasks.forEach(function (task) {
    task_names.push(task.name);    
});
 
console.log(task_names) 
```

**Output**

```node
0: "Write for Learning"
1: "Work out"
2: "Movie"
```

**Map**

```node 
const task_names = tasks.map(function(task, index, array){
    return task.name;
})
console.log(task_names)
```

**Output**

```node
0: "Write for Learning"
1: "Work out"
2: "Movie"
```


**Filter**

```node 
const words = ['Python', 'Javascript', 'Go', 'Java', 'PHP', 'Ruby'];
const result = words.filter(word => word.length < 8);
console.log(result);
```

**Output**

```node
0: "Python"
1: "Go"
2: "Java"
3: "PHP"
4: "Ruby"
```

**Reduce**

```node 
const total = [1, 2, 3, 4, 5].reduce(function (previous, current, index) {
    const val = previous + current;
    console.log("The previous value is " + previous + 
                "; the current value is " + current +
                ", and the current iteration is " + (index + 1));
    return val;
}, 0);
```

**Output**

```node
The previous value is 0; the current value is 1, and the current iteration is 1
map-filter-reduce.html:90 The previous value is 1; the current value is 2, and the current iteration is 2
map-filter-reduce.html:90 The previous value is 3; the current value is 3, and the current iteration is 3
map-filter-reduce.html:90 The previous value is 6; the current value is 4, and the current iteration is 4
map-filter-reduce.html:90 The previous value is 10; the current value is 5, and the current iteration is 5
```

**Reduce - Example 2**

**HTML**

```node 
<p id="demo"></p>
```

```node 
const numbers = [175, 50, 25];

document.getElementById("demo").innerHTML = numbers.reduce(myFunc);

function myFunc(total, num){
    return total - num;
}
```

**Output**

```node
100
```


**Reference**
[ap, Filter, and Reduce](https://zonayed.js.org/daily/post-1),
[How to Use Map, Filter, and Reduce in JavaScript](https://code.tutsplus.com/tutorials/how-to-use-map-filter-reduce-in-javascript--cms-26209),
[JavaScript Map, Reduce, and Filter](https://www.freecodecamp.org/news/javascript-map-reduce-and-filter-explained-with-examples/),
[.map(), .reduce(), and .filter()](https://medium.com/poka-techblog/simplify-your-javascript-use-map-reduce-and-filter-bd02c593cc2d),
