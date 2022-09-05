### JavaScript Async/await
async and await make promises easier to write


**Async/await ?**

- async makes a function return a Promise
- await makes a function wait for a Promise

**Promise**


```node 
        let result = function(score){
            return new Promise(function(resolve, reject){
                console.log("Calculating results...")
                if(score>50){
                    resolve("Congratulation! You have passed")
                }else{
                    reject("You have failed")
                }
            })
        }
        let grade = function(response){
            return new Promise(function(resolve, reject){
                console.log("Calculating your grade...")
                resolve("Your grade is A. " + response)
            })
        }
        result(80).then(response => {
            console.log("Result Received")
            return grade(response)
        }).then(finalgrade => {
            console.log(finalgrade)
        }).catch(err => {
            console.log(err)
        })
```

**Output**

```node
Calculating results...
Result Received
Calculating your grade...
Your grade is A. Congratulation! You have passed
```

**Async/await**


```node
        async function calculateResults(){
            try{
                const response = await result(80);
                console.log("Results Received");
                const finalgrade = await grade(response)
                console.log(finalgrade)
            }catch(err){
                console.log(err)
            }
        }
        calculateResults()
```
**Output**

```node
Calculating results...
Result Received
Calculating your grade...
Your grade is A. Congratulation! You have passed
```


**Reference**

[JavaScript Loops Explained](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)