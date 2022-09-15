### JavaScript Merge objects
To merge objects into a new one that has all properties of the merged objects, you have two options:

1. Use a spread operator ( ...)
2. Use the Object.assign() method

**Merge objects using the spread operator (...)**

ES6 introduced the spread operator (...) which can be used to merge two or more objects and create a new one that has properties of the merged objects.

```node 
let person = {
    firstName: 'Bipon',
    lastName: 'Biswas',
    age: 25,
    ssn: '123-456-2356'
};

let job = {
    jobTitle: 'JavaScript Developer',
    location: 'USA'
};

let employee = {
    ...person,
    ...job
};

console.log(employee);

```

**Output:**

```
{
    firstName: 'Bipon',
    lastName: 'Biswas',
    age: 25,
    ssn: '123-456-2356',
    jobTitle: 'JavaScript Developer',
    location: 'USA'
}
```

If objects have a property with the same name, then the right-most object property overwrites the previous one. For example:

```node 
let job = {
    jobTitle: 'JavaScript Developer',
    country: 'USA'
};

let location = {
    city: 'London',
    country: 'England'
};

let remoteJob = {
    ...job,
    ...location
};

console.log(remoteJob);


```

**Output:**

```
{
    jobTitle: 'JavaScript Developer',
    country: 'England',
    city: 'London'
}

```

In this example, the **job** and **location** has the same property **country**. When we merged these objects, the result object **(remoteJob)** has the **country** property with the value from the second object **(location)**.


**Merge objects using Object.assign() method**

The Object.assign() method allows you to copy all enumerable own properties from one or more source objects to a target object, and return the target object:

```node
Object.assign(target, sourceObj1, sourceObj2, ...);
```
Similar to spread operator ( ...), if the source objects have the same property name, the later object will overwrite the previous object. See the following example:

```
let person = {
    firstName: 'Bipon',
    lastName: 'Biswas',
    age: 25,
    ssn: '123-456-2356'
};

let job = {
    jobTitle: 'JavaScript Developer',
    country: 'BD'
};

let employee = Object.assign(person, job);
console.log(employee);
```

**Output:**

```
{
    firstName: 'Bipon',
    lastName: 'Biswas',
    age: 25,
    ssn: '123-456-2356',
    jobTitle: 'JavaScript Developer',
    country: 'BD'
}

```

**The Shallow Merge**

Both the spread operator ( ...) and Object.assign() method perform a shallow merge. It means that if an object has a property that references to another object, the property of the original object and result target object will reference the same object. For example:

```node 
let person = {
    firstName: 'Bipon',
    lastName: 'Biswas',
    age: 25,
    ssn: '123-456-2356',
    contact: {
        phone: '408-989-8745',
        email: 'bipon.biswas@example.com'
    }
};


let job = {
    jobTitle: 'JavaScript Developer',
    location: 'USA'
};

let employee = { ...person,  ...job };

console.log(employee.contact === person.contact);
```


**Output**

```
true
```



**Reference**

[JavaScript Merge Objects](https://www.javascripttutorial.net/object/javascript-merge-objects/)
