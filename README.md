# erlang 在线实验环境

## 软件简介

Erlang是一种编程语言，用于构建具有高可用性要求的大规模可扩展软实时系统。其中一些用途是电信，银行，电子商务，计算机电话和即时通讯。Erlang的运行时系统内置了对并发，分发和容错的支持。

所属类型是编程语言

特点：

- 并发性 - Erlang支持超大量级的并发进程，并且不需要操作系统具有并发机制。
- 分布式 - 一个分布式Erlang系统是多个Erlang节点组成的网络（通常每个处理器被作为一个节点）
- 健壮性 - Erlang具有多种基本的错误检测能力，它们能够用于构建容错系统。
- 软实时性- Erlang支持可编程的“软”实时系统，使用了递增式垃圾收集技术。
- 热代码升级-Erlang允许程序代码在运行系统中被修改。旧代码能被逐步淘汰而后被新代码替换。在此过渡期间，新旧代码是共存的。
- 递增式代码装载-用户能够控制代码如何被装载的细节。
- 外部接口-Erlang进程与外部世界之间的通讯使用和在Erlang进程之间相同的消息传送机制。
- Fail-fast（中文译为速错），即尽可能快的暴露程序中的错误。
- 面向并发的编程(COP concurrency-oriented programming)
- 函数式编程
- 动态类型
- 及早求值或严格求值
- 支持脚本运行


## 软件官网

http://www.erlang.org/

## Dockerfile 使用方法

运行它作为REPL
```
➸ docker run -it --rm erlang
Erlang/OTP 18 [erts-7.1] [source] [64-bit] [smp:8:8] [async-threads:10] [hipe] [kernel-poll:false]

Eshell V7.1  (abort with ^G)
1> uptime().
3 seconds
ok
2>                                 % use Ctrl+G to call the shell switch
User switch command
 --> ?
  c [nn]            - connect to job
  i [nn]            - interrupt job
  k [nn]            - kill job
  j                 - list all jobs
  s [shell]         - start local shell
  r [node [shell]]  - start remote shell
  q                 - quit erlang
  ? | h             - this message
 --> q
➸ docker run -it --rm -h erlang.local erlang erl -name snode@erlang.local
Erlang/OTP 18 [erts-7.1] [source] [64-bit] [smp:8:8] [async-threads:10] [hipe] [kernel-poll:false]

Eshell V7.1  (abort with ^G)
(snode@erlang.local)1> erlang:system_info(otp_release).
"18"
(snode@erlang.local)2>
User switch command
--> q
```
运行单个Erlang escript
```
$ docker run -it --rm --name erlang-inst1 -v "$PWD":/usr/src/myapp -w /usr/src/myapp erlang escript your-escript.erl
```
## 资源链接

- http://www.cnerlang.com/
- http://www.erlang.org/
