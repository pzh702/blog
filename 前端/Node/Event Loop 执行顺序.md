[详解 promise.then,process.nextTick, setTimeout 以及 setImmediate 的执行顺序。](https://www.jianshu.com/p/a39d3e878d06)

看一段代码
```
setImmediate(() => {
console.log(1);
setTimeout(() => {
console.log(2);
}, 100);
setImmediate(() => {
console.log(3);
});
process.nextTick(() => {
console.log(4);
});
});
process.nextTick(() => {
console.log(5);
setTimeout(() => {
console.log(6);
}, 100);
setImmediate(() => {
console.log(7);
});
process.nextTick(() => {
console.log(8);
});
});
console.log(9);
```

输出：9 5 8 1 7 4 3 6 2

解释：优先级 nextTick>setImmediate>setTimeout，同优先级的任务，先创建的先执行；不同任务，先执行优先级高的。
1. 创建setImmediate，nextTick任务，输出9
2. 执行nextTick任务：输出5，创建setTimeout、setImmediate、nextTick任务
3. 执行nextTick输出8，此时剩下setImmediate和setTimeout，先执行setImmediate：输出1，创建setTimeout、setImmediate、nextTick任务，并且输出7
4. 此时除了setTimeout又多了nextTick和setImmediate任务，按照优先级依次输出4362
