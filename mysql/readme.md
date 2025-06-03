# mysqlKill

## 使用场景

循环查杀符合某些特征的mysql会话。

## 参数说明

```azure
Usage of ./mysqlKill:
    -P int
        数据库端口 (default 3306)
  -busy-time int
        语句执行秒数大于等于此参数值的会话会被杀掉 (default 60)
  -h string
        数据库地址
  -interval int
        多久执行一次检查，单位：秒 (default 10)
  -match-db string
        匹配数据库（可以指定多个，逗号分隔）
  -match-sql string
        搜索sql文本（支持%模糊匹配）
  -match-user string
        匹配用户（可以指定多个，逗号分隔）
  -mode string
        dry-run: 只打印匹配的线程，不会执行kill。
kill: 终止匹配的线程。
kill-query: 终止匹配的查询，线程不退出。 (default "dry-run")
  -p string
        登录密码
  -run-time string
        运行时间，举例：1d,1h,1m,1s (default "365d")
  -u string
        登录用户
```

> -u: 登录用户,需要有kill权限。
> -busy-time: 执行时间（秒）大于等于此参数值的会话会被杀掉。         
> -run-time：运行时间超过此参数值程序会退出，默认365天。支持指定天、小时、分钟、秒，举例：1h30m 表示程序运行1小时30分钟后退出。      
> -dry-run: 模拟运行模式，此模式下只打印符合kill的会话，不会执行kill操作。用于验证参数设置是否正确。     




