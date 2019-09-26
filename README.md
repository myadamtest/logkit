### Usage

#### Init

```go
logkit.Init("logname", logkit.LevelDebug)
```

```go
logkit.AlsoStdout(true)
// or
xxx -alsostdout
```

#### 支持Flag
支持通过Flag覆盖原有设置：
- `alsostdout` 同时写到stdout
- `loglevel`  debug|info|warn|error
- `logname`  log name
- `logpath` 只针对 filelog 有效，设置 log 路径

#### 优雅退出
文件Log下，由于log缓存的问题，需要在退出时保证Log完全刷盘到硬盘，logkit 提供了两种优雅退出方式：

1. 在退出时手动调用`Exit` 函数

```go
logkit.Exit()
```

####  Is Debug

判断是否Debug Level:
```go
logkit.IsDebug()
```
#### Action 日志

将以 json格式记录日志，用于特殊统计需求

```go
logkit.Action("action", fields)
```
