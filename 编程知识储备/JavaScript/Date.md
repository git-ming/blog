# Date


## API

| 方法名 | 描述 | 参数 |
| --- | --- | --- |
| getFullYear | 年，1000到9999的四位数 |  |
| getMonth | 月，从0开始 |  |
| getDate | 日 |  |
| getDay | 周几 |  |
| getHours | 时 |  |
| getUTCHours| UTC的时，其他类似 |  |
| getMinutes | 分 |  |
| getSeconds | 秒 |  |
| getMilliseconds | 毫秒 |  |
| getTime | UTC时间到该日期的毫秒数,和时区有关 |  |
| now | UTC到当前时间的毫秒数,和时区有关。es5 支持 | |
| UTC| 获取UTC时间 |  |
| getTimezoneOffset| 获取相对UTC偏移的分钟原因，有的地区不够一个小时的时区 |  |
| UTC| 获取UTC时间 |  |
| setFullYear | 设置年，其他类似 | yearValue[, monthValue[, dayValue]] |



### UTC
协调世界时，为原子钟报时。名字是由CUT和TUC英法对应缩写，妥协而来。
### GMT
格林尼治标准时间，指太阳横穿格林尼治子午线的时间，因为最大误差达16分钟，所以不再用于标准时间

## 工具方法
### 初始化
定义好日期的格式，精确度

### 转换格式
业务常用的有`yyyy-MM-dd`,`yyyy/MM/dd`,时间戳1499670385613,日期对象这三种。此外，可能有`[2017,7,10]`,`{y:2016,M:7}`。

入参: 任意格式日期，转换模板
出参: 对应格式的日期

注意：精确度，可以取整，可以精确到对应单位

```
new UtilDate(Date).transform(template)
```
### 比较先后

```
new UtilDate(Date1).isBefore(Date2)
```

### 相对增减
比如当前时间半小时后

```
new UtilDate(Date).add('0.5H')
```

## 常见问题
### 客户端 vs 服务端
客户端的时间跟系统有关，如果调整了对应的时区，时间，会导致对应的时间不对。
所以都是以server端的时间为基准，可以保证所有端的时间一致。
### 时区
同一个时间戳，不同的时区展示的时间不同。
### 如何保证当前时间实时有效
服务端一次拉取就不变了。两种方案：开长连接，一致获取；模拟时间计时，做`setIntervel`。

### NaN
case覆盖不全，比如“”转换成了“NaN-NaN-NaN”




Q

