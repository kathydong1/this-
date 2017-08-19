this指向
  全局函数---》this指向window
  事件函数--》指向事件
  定时器内--》指向window
  函数套函数，内函数---》window
  es6函数--》指向父级


注意：普通函数只有在声明式中如果有"use strict"，这里的this指向underfine

var fn=()=>alert(1);//相当于return alert（1），且当不传参数时必须用（）
fn()
var f=()=>{执行的代码}
var fn=(a)=>代码   ||  var fn= a =>代码
var fn=(a,b,c)=>代码     括号不能省略,否则报错
箭头函数的this，永远指向定义的父级，（箭头函数不能new）
 正常函数的this，看有没有主，有就是该主，没有是window
this的优先级：人为手动设置>new>定时器>事件>fn()   
   		       
 事件函数是不能用箭头函数的，因为this指向改变了，是Window
 "use strict"==严格模式，
   		      如果直接函数名（），this指向是underfine（主要是用在this，上，正常能够指向Windows的用了严格模式，就是underfine）
   		      如果在事件绑定中，this指向不变
   		      只要fn()函数名加()前面没有主或者没有call改变this的方法，那么this就是window
   		      JS规范，直接new函数下的*内置*方法就报错，自定义的不会报错
   		       同样箭头函数也是不能new的，否则报错
