前言
ztest是一个测试报告，报告清晰简单，有饼图，汇总，运行详情。有兴趣的可以下载试用！

使用方式
将报告的json数据替换template文件中的${resultData}即可。

pull ztest。
读取template文件数据。
将测试报告数据json序列化。
用json序列化后的数据替换读取的template文件中的${resultData}。比如：
Gson gson = new GsonBuilder().disableHtmlEscaping().create();
String template = FileUtil.read(templatePath);
template = template.replaceFirst("\\$\\{resultData\\}", gson.toJson(result));
output.write(template);
将替换后的数据写入一个html文件(比如report.html)即可。
测试报告数据格式示例：
{
    "testPass": 1,
    "testResult": [
        {
            "className": "com.test.testcase.TestDemo1",
            "methodName": "testDemo",
            "description": "测试DEMO",
            "spendTime": "11ms",
            "status": "成功",
            "log": [
                "this is demo!"
            ]
        }
    ],
    "testName": "20171109132744897",
    "testAll": 1,
    "testFail": 0,
    "beginTime": "2017-11-09 13:27:44.917",
    "totalTime": "11ms",
    "testSkip": 0
}
Java TestNg使用示例
请参考ztest中的TestDemo1.java ZTestReport.java

报告展示
ztest

