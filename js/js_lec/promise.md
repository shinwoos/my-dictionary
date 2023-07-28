# Promise

**Promise** 는 class 입니다.

**new**로 객체를 만들어서 사용해야 합니다.

**callback** 함수의 중복을 막기 위함으로 쓰입니다. ex) *callback hell*

아래 예제는 *callback hell* 을 **Promise**를 사용해 *callback hell*이 발생하지 않습니다.

*callback hell* : 일련의 처리 후 다음 함수의 매개변수로 값을 연속적으로 넘겨주는 행위 [예제보기](#callback-hell-example)

```javascript

class UserStorage{
    loginUser(id, pwd){
        return new Promise((resolve, reject) => {
            setTimeout(()=>{
                if(
                    (id == "shin" && pwd == "1234" || id == "woo" && pwd == "1234")
                ){
                    resolve(id);
                }else{
                    reject(new Error("not found"));   
                }
            }, 2000);
        });
    }

    getRole(user){
        return new Promise((resolve, reject) => {
            setTimeout(()=>{
                    if(user === "shin"){
                            resolve({name:"shin", role:"admin"});
                    }else{
                            reject(new Error("no access"));
                    }
            }, 1000);
        })
    }
}

const userStorage = new UserStorage();

const id = "woo";
const pwd = "1234";

userStorage
    .loginUser(id, pwd)
    .then(userStorage.getRole)
    .then(user => console.log(`hello ${user.name}, have a ${user.role} role`))
    .catch(error => console.log(error));


```
<br>

### *callback hell example*


```javascript
function(){
    function(){
        function(){
            function(){
                     ......
            }
        }
    }
}
```
