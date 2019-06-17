# webpackStudyNew
moment-timezone的常用方法
moment-timezone用于做时间时区的附加与转换，比较常用的方法是

给定一个时间，把这个时间加上时区
给定一个时间，把这个时间转成指定时区的时间
获取指定时区的当前时间

看下面的例子：
let moment = require('moment-timezone');

let time = "2019-01-30 11:00";
console.log(moment.tz(time, "America/Los_Angeles").format()); //给已知时间加上时区
console.log(moment(time).tz("America/Los_Angeles").format());  //将已知之间转换到指定时区的时间
console.log(moment().tz("America/Los_Angeles").format()); //获取指定时区的当前时间

结果
2019-01-30T11:00:00-08:00
2019-01-29T19:00:00-08:00
2019-01-29T19:15:04-08:00
moment会自动区分冬令时和夏令时的交替：比如改下时间到8月份（夏令时），时区会自动切换成西7区。
time = "2018-08-30 11:00";
console.log(moment.tz(time, "America/Los_Angeles").format()); //给已知时间加上时区
console.log(moment(time).tz("America/Los_Angeles").format());  //将已知之间转换到指定时区的时间


结果：
2018-08-30T11:00:00-07:00
2018-08-29T20:00:00-07:00

作者：V_Jan
链接：https://www.jianshu.com/p/912c258dfc24
来源：简书
简书著作权归作者所有，任何形式的转载都请联系作者获得授权并注明出处。

const dd = moment.tz.guess();
console.log(dd,4444444);// Asia/Shanghai 4444444
