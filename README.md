Redis源码阅读轨迹
=============
一、基础数据结构
-------------
* 内存分配 [zmalloc.h](/src/zmalloc.h)、[zmalloc.c](/src/zmalloc.c)、[sdsalloc.h](/src/sdsalloc.c)
* 简单动态字符串 [sds.h](/src/sds.h)和[sds.c](/src/sds.c)
* 双端链表 [adlist.h](/src/adlist.h)和[adlist.c](/src/adlist.c)
* 字典 [dict.h](/src/dict.h)和dict.c
* 跳跃表 server.h（zskiplist以及zskiplistNode结构）和t_zset.c(zsl开头的函数)
* 整数集合 intset.h和intset.c
* 压缩列表 ziplist.h和ziplist.c
* 压缩字典 zipmap.h和zipmap.c
* 快速链表 quicklist.h和quicklist.c
* 基数统计 hyperloglog.c(hllhdr结构, hll 开头的函数)
* geohash geohash.h、geohash.c

二、Redis数据类型
-------------
* 对象系统 object.c
* 字符串键 t_string.c
* 列表建 t_list.c
* 哈希键 t_hash.c
* 集合键 t_set.c
* 有序集合键 t_zset.c(除zsl开头的所有函数)
* HyperLogLog键 hyperloglog.c(pf开头的函数)
* 地理位置 geo.h、geo.c

三、Redis数据库
-------------
* 数据库实现 db.c
* 通知功能 notify.c
* RDB持久化 rdb.h和rdb.c
* AOF持久化 aof.c

四、客户端/服务端
-------------
* 事件处理模块 ae.h、ae.c、ae_epoll.c、ae_evport.c、ae_kqueue.c、ae_select.c
* 网路链接库 anet.h、anet.c、networking.c
* 服务器端 server.h和server.c
* 客户端 redis-cli.c

五、分布式Redis
-------------
* 复制功能 replication.c
* Redis哨兵 sentinel.c
* Redis集群 cluster.h和cluster.c

六、独立功能模块
-------------
* 发布和订阅 pubsub.c
* 事务 

七、测试
-------------
* 内存检测 memtest.c
* redis性能测试 redis_benchmark.c
* 更新日志检查 redis_check_aof.c
* 本地数据库检查 redis_check_rdb.c
* C风格的小型测试框架 testhelp.c

八、工具类
-------------
* 二进制位操作命令 bitops.c
* 调试 debug.c
* 高低位转换 endianconv.h和endianconv.c(适配不同系统)
* 辅助于命令的提示信息 help.h
* 压缩算法 lzf.h、lzf_c.c、lzf_d.c、lzfP.h
* 随机数 rand.h和rand.c
* 版本发布 release.c
* sha加密算法 sha1.h和sha1.c
* 通用工具类 util.h和util.c
* 循环冗余校验 crc16.c、crc64.h、crc64.c
* SORT命令 sort.c
* 伪随机函数 siphash.c
* 进程信息操作 setproctitle.c
* geo工具类 geohash_helper.h、geohash_helper.c

九、封装类
-------------
* 后台线程I/O bio.h和bio.c
* 延迟类 latency.h和latency.c
* 排序算法类 pqsort.h和pqsort.c
* Redis定义的I/O类 rio.h、rio.c、syncio.c
* 同步Socket和文件I/O操作 syncio.c

十、其他
-------------
* 微线图 sparkline.h和sparkline.c
* 慢日志 slowlog.h和slowlog.c
* 脚本 scripting.c
* 过期机制 expire.c