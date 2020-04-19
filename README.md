# domain_fuzz
一个全方位无死角的域名爆破工具。

# 说明&用法
* -u 目标链接：http://$$.mi.com 则表示爆破mi.com的子域名，$$为标记点，想爆哪里就放在那里
* -r 字典范围：默认字典长度为1-4位数所有可能组合，加上该参数表示使用自定义长度。例：-r 1-4表示1-4位字母所有可能组合，-r 4表示4位字母所有可能组合
* -t 线程：默认20个线程，该参数表示自定义线程数
* -o 请求模式：默认GET模式，加上该参数表示使用head请求方式
* -m 字典模式：默认26个字母所有可能排序，加上该参数表示在字母基础上加上0-9的数字

# 例子
爆破小米的子域名，使用默认字典范围(26个字母组成1-4位所有可能排序的字典)、默认线程（20）、默认GET方式请求、默认字典模式
```code
python3 domain_fuzz.py -u http://$$.mi.com
```
![](https://raw.githubusercontent.com/autoing/domain_fuzz/master/get.png)


爆破小米的子域名，使用自定义字典范围(26个字母组成1-5位所有可能排序的字典)、线程（50）、HEAD方式请求、默认字典模式
```code
python3 domain_fuzz.py -u http://$$.mi.com -r 1-5 -t 50 -o
```
![](https://raw.githubusercontent.com/autoing/domain_fuzz/master/head.png)

# 注意
不要生成超过6位数的字典，因为有308915776种组合模式，这时候需要量子宽带和天河一号才能跑。

# 字典长度说明

