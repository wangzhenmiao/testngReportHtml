前言
报告清晰简单，有饼图，汇总，运行详情。有兴趣的可以下载试用！

使用方式
将报告的json数据替换template文件中的${resultData}即可。

1、实现IReporter接口，重写generateReport方法
2、报告的css+html样式在template中，默认放在根目录下
3、在用例的类前，加注释@Listeners，实现调用
4、生成的报告默认在根目录下 report.html

注意：
1、report.html报告已经将调用的js脚本写到html中了，并没有其他依赖，可以单独看效果
2、outlook邮箱，不能解析JavaScript脚本，会导致html报告显示不正常


参考github的地址：https://github.com/zhangfei19841004/ztest


