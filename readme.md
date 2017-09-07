> 一个基于免费接口获取数据，并处理数据，从而方便判断天朝工作日的工具
2017-09-06

* 纯PHP
* 第三方接口用的是[聚合数据的万年历](https://www.juhe.cn/docs/api/id/177)

## 更新

### 2017-09-07

- 增加判断，减少已经循环已经处理过的节日
- 增加判断，区分多个假日和单个假日数据格式不同


## 处理

- 通过聚合数据的`最近假日`来逐月获取假日信息
- 将获取的数据进行自定义处理,并“缓存”起来
- 之后的判断直接使用

## 其他

- 使用接口需要[注册](https://www.juhe.cn/register)聚合数据的账号，并[申请](https://www.juhe.cn/docs/api/id/177)对应的数据；在工具中需要填入对应的`appkey`

- 组装的数据可以存放到任何文件或者任何存储中，本例为了使用方便，直接存到`php`文件中,最好放到缓存中

- 按年份存的

- 组装的数据格式
```
...

'2016-12-31' => 
  array (
    'status' => 3,
  ),
  '2017-1-1' => 
  array (
    'status' => 3,
  ),
...

```
这里定义的`status`的值,工作日为1，休息日为2（加班2倍工资），节假日为3（加班应该是3倍工资），方便计算O(∩_∩)O。


