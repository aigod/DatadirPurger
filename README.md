# DatadirPurger
数据目录和快照目录会分别生成log.n, snapshot.n的日志文件。而且每次事物的更新，都会重新生成一个新的日志文件，且n会加1。随着提交的事物越来越多，文件就会越来越大。因此实现了一个定期清理的守护进程，每隔60秒（参数可改）进行清理，只保留最近的3个（参数可改）版本。