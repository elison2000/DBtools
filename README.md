# DBtools 数据库工具集（面向DBA或开发）

## public工具集

### DBstat

> 查看数据库实例负载和状态信息，类似top命令，支持多种数据库版本：mysql,oracle,mongo,postgresql,redis。

### checkData

> 核对2个数据库是否一致， 支持多种数据库版本：mysql,oceanbase,doris,mongo,postgresql,sql server等。

## mysql工具集

### mysqlKill

> 循环查杀符合某些特征的mysql会话，类似pt-kill，但比pt-kill更好用。

## redis工具集

### rma
> 分析rdb文件内存使用情况，支持前缀分析，支持多种输出结果。

### find_big_keys
> 根据match参数模糊搜索key名，找到占用内存（估算值）大于100KB（可通过size参数修改）的key，保存到key_list.txt文件。

### find_nottl_keys
> 查找没有设置过期时间的key，保存到key_list.txt文件。

### get_slowlog
>  导出慢查询，保存到csv文件。

### get_value
> 导出指定key的value值。

### scan_keys
> 根据match参数模糊搜索key名，保存到 key_list.txt 文件。

### unlink_keys
> 根据 key_list.txt 中的key，执行删除操作。 key_list.txt 文件内容是keyName集合,一行为一个key。
> 该工具和scan_keys结合使用：
> 1. scan_keys 找到要删除的key，手工编辑key_list.txt文件，剔除不需要做删除的key。
> 2. 执行unlink_keys 删除key_list.txt 中的key。