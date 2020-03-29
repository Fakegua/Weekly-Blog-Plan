## 用法

```
(new Promise(asyncFunc)).then(data => {
    ... operation for data
}).catch(err => {
    ... operation for err
})
```

或者

```
(new Promise(asyncFunc).then(data => {
    ... operation for data
}, err => {
    .. operation for data
}))
```

## 定义
Promise 是一个类似于状态机的对象
