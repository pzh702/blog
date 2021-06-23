详解 promise.then,process.nextTick, setTimeout 以及 setImmediate 的执行顺序。https://www.jianshu.com/p/a39d3e878d06

看一段代码
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

输出：9 5 8 1 7 4 3 6 2

解释：优先级 nextTick>setImmediate>setTimeout，同优先级的任务，先创建的先执行；不同任务，先执行优先级高的。
