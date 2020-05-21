# pytest-zh-CN
自己在学习pytest时，发现尚未有完整的中文版本，给一些英语不那么好的同志阅读带来了一些困难，所以我在学习的同时，整理了一下翻译的文字，供大家学习参考。因本人英文水平也不是很高，翻译难免会存在纰漏，欢迎大家指出，我会及时更正。若大家有更好的翻译版本，也希望能够互相交流。

### 目录

[下载最新版本的pdf](https://media.readthedocs.org/pdf/pytest/latest/pytest.pdf)

* #### [安装和入门](https://github.com/CHSherlock/pytest-zn/blob/master/%E5%AE%89%E8%A3%85%E5%92%8C%E5%85%A5%E9%97%A8.md)
    * [安装pytest](https://github.com/CHSherlock/pytest-zn/blob/master/%E5%AE%89%E8%A3%85%E5%92%8C%E5%85%A5%E9%97%A8.md#安装pytest)
    * [创建您的第一个测试](https://github.com/CHSherlock/pytest-zn/blob/master/%E5%AE%89%E8%A3%85%E5%92%8C%E5%85%A5%E9%97%A8.md#创建您的第一个测试)
    * [运行多个测试](https://github.com/CHSherlock/pytest-zn/blob/master/%E5%AE%89%E8%A3%85%E5%92%8C%E5%85%A5%E9%97%A8.md#运行多个测试)
    * [断言会引发某些异常](https://github.com/CHSherlock/pytest-zn/blob/master/%E5%AE%89%E8%A3%85%E5%92%8C%E5%85%A5%E9%97%A8.md#断言会引发某些异常)
    * [将一个类中的多个测试分组](https://github.com/CHSherlock/pytest-zn/blob/master/%E5%AE%89%E8%A3%85%E5%92%8C%E5%85%A5%E9%97%A8.md#将一个类中的多个测试分组)
    * [请求一个唯一的临时目录来进行函数测试](https://github.com/CHSherlock/pytest-zn/blob/master/%E5%AE%89%E8%A3%85%E5%92%8C%E5%85%A5%E9%97%A8.md#请求一个唯一的临时目录来进行函数测试)
    * [继续阅读](https://github.com/CHSherlock/pytest-zn/blob/master/%E5%AE%89%E8%A3%85%E5%92%8C%E5%85%A5%E9%97%A8.md#继续阅读)

* #### [使用和调用](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md)
    * [调用pytest通过python -m pytest](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E8%B0%83%E7%94%A8pytest%E9%80%9A%E8%BF%87python--m-pytest)
    * [可能会看到的退出代码](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E5%8F%AF%E8%83%BD%E4%BC%9A%E7%9C%8B%E5%88%B0%E7%9A%84%E9%80%80%E5%87%BA%E4%BB%A3%E7%A0%81)
    * [获取有关版本，选项名称，环境变量的帮助](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E8%8E%B7%E5%8F%96%E6%9C%89%E5%85%B3%E7%89%88%E6%9C%AC%E9%80%89%E9%A1%B9%E5%90%8D%E7%A7%B0%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F%E7%9A%84%E5%B8%AE%E5%8A%A9)
    * [在第一次(或N次)失败后停止](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E5%9C%A8%E7%AC%AC%E4%B8%80%E6%AC%A1%E6%88%96n%E6%AC%A1%E5%A4%B1%E8%B4%A5%E5%90%8E%E5%81%9C%E6%AD%A2)
    * [指定测试/选择测试](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E6%8C%87%E5%AE%9A%E6%B5%8B%E8%AF%95%E9%80%89%E6%8B%A9%E6%B5%8B%E8%AF%95)
    * [修改Python的回溯打印](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E4%BF%AE%E6%94%B9python%E7%9A%84%E5%9B%9E%E6%BA%AF%E6%89%93%E5%8D%B0)
    * [详细的总结报告](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E8%AF%A6%E7%BB%86%E7%9A%84%E6%80%BB%E7%BB%93%E6%8A%A5%E5%91%8A)
    * [失败时切换到PDB (Python调试器)](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E5%A4%B1%E8%B4%A5%E6%97%B6%E5%88%87%E6%8D%A2%E5%88%B0pdb-python%E8%B0%83%E8%AF%95%E5%99%A8)
    * [在测试开始时跳到PDB (Python调试器)](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E5%9C%A8%E6%B5%8B%E8%AF%95%E5%BC%80%E5%A7%8B%E6%97%B6%E8%B7%B3%E5%88%B0pdb-python%E8%B0%83%E8%AF%95%E5%99%A8)
    * [设置断点](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E8%AE%BE%E7%BD%AE%E6%96%AD%E7%82%B9)
    * [使用内置的断点函数](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E4%BD%BF%E7%94%A8%E5%86%85%E7%BD%AE%E7%9A%84%E6%96%AD%E7%82%B9%E5%87%BD%E6%95%B0)
    * [分析测试执行时间](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E4%BD%BF%E7%94%A8%E5%86%85%E7%BD%AE%E7%9A%84%E6%96%AD%E7%82%B9%E5%87%BD%E6%95%B0)
    * [错误处理程序](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E9%94%99%E8%AF%AF%E5%A4%84%E7%90%86%E7%A8%8B%E5%BA%8F)
    * [创建JUnitXML格式的文件](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E5%88%9B%E5%BB%BAjunitxml%E6%A0%BC%E5%BC%8F%E7%9A%84%E6%96%87%E4%BB%B6)
    * [创建resultlog格式的文件](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E5%88%9B%E5%BB%BAresultlog%E6%A0%BC%E5%BC%8F%E7%9A%84%E6%96%87%E4%BB%B6)
    * [将测试报告发送到在线pastebin服务](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E5%88%9B%E5%BB%BAresultlog%E6%A0%BC%E5%BC%8F%E7%9A%84%E6%96%87%E4%BB%B6)
    * [提前加载插件](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E5%88%9B%E5%BB%BAresultlog%E6%A0%BC%E5%BC%8F%E7%9A%84%E6%96%87%E4%BB%B6)
    * [禁用插件](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E5%88%9B%E5%BB%BAresultlog%E6%A0%BC%E5%BC%8F%E7%9A%84%E6%96%87%E4%BB%B6)
    * [从Python代码中调用pytest](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%92%8C%E8%B0%83%E7%94%A8.md#%E5%88%9B%E5%BB%BAresultlog%E6%A0%BC%E5%BC%8F%E7%9A%84%E6%96%87%E4%BB%B6)

* #### [将pytest与现有测试套件一起使用](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E5%B0%86pytest%E4%B8%8E%E7%8E%B0%E6%9C%89%E6%B5%8B%E8%AF%95%E5%A5%97%E4%BB%B6%E4%B8%80%E8%B5%B7%E4%BD%BF%E7%94%A8.md)
    * [使用pytest运行现有的测试套件](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E5%B0%86pytest%E4%B8%8E%E7%8E%B0%E6%9C%89%E6%B5%8B%E8%AF%95%E5%A5%97%E4%BB%B6%E4%B8%80%E8%B5%B7%E4%BD%BF%E7%94%A8.md#%E4%BD%BF%E7%94%A8pytest%E8%BF%90%E8%A1%8C%E7%8E%B0%E6%9C%89%E7%9A%84%E6%B5%8B%E8%AF%95%E5%A5%97%E4%BB%B6)

* #### [测试中断言的编写和报告](https://github.com/CHSherlock/pytest-zh-CN/tree/master#%E6%B5%8B%E8%AF%95%E4%B8%AD%E6%96%AD%E8%A8%80%E7%9A%84%E7%BC%96%E5%86%99%E5%92%8C%E6%8A%A5%E5%91%8A)
    * [使用assert语句进行断言](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E6%B5%8B%E8%AF%95%E4%B8%AD%E6%96%AD%E8%A8%80%E7%9A%84%E7%BC%96%E5%86%99%E5%92%8C%E6%8A%A5%E5%91%8A.md#%E4%BD%BF%E7%94%A8assert%E8%AF%AD%E5%8F%A5%E8%BF%9B%E8%A1%8C%E6%96%AD%E8%A8%80)
    * [关于预期异常的断言](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E6%B5%8B%E8%AF%95%E4%B8%AD%E6%96%AD%E8%A8%80%E7%9A%84%E7%BC%96%E5%86%99%E5%92%8C%E6%8A%A5%E5%91%8A.md#%E5%85%B3%E4%BA%8E%E9%A2%84%E6%9C%9F%E5%BC%82%E5%B8%B8%E7%9A%84%E6%96%AD%E8%A8%80)
    * [关于预期警告的断言](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E6%B5%8B%E8%AF%95%E4%B8%AD%E6%96%AD%E8%A8%80%E7%9A%84%E7%BC%96%E5%86%99%E5%92%8C%E6%8A%A5%E5%91%8A.md#%E5%85%B3%E4%BA%8E%E9%A2%84%E6%9C%9F%E5%BC%82%E5%B8%B8%E7%9A%84%E6%96%AD%E8%A8%80)
    * [利用上下文相关的比较](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E6%B5%8B%E8%AF%95%E4%B8%AD%E6%96%AD%E8%A8%80%E7%9A%84%E7%BC%96%E5%86%99%E5%92%8C%E6%8A%A5%E5%91%8A.md#%E5%85%B3%E4%BA%8E%E9%A2%84%E6%9C%9F%E5%BC%82%E5%B8%B8%E7%9A%84%E6%96%AD%E8%A8%80)
    * [为失败的断言定义自己的解释](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E6%B5%8B%E8%AF%95%E4%B8%AD%E6%96%AD%E8%A8%80%E7%9A%84%E7%BC%96%E5%86%99%E5%92%8C%E6%8A%A5%E5%91%8A.md#%E5%85%B3%E4%BA%8E%E9%A2%84%E6%9C%9F%E5%BC%82%E5%B8%B8%E7%9A%84%E6%96%AD%E8%A8%80)
    * [断言自省的详细信息](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E6%B5%8B%E8%AF%95%E4%B8%AD%E6%96%AD%E8%A8%80%E7%9A%84%E7%BC%96%E5%86%99%E5%92%8C%E6%8A%A5%E5%91%8A.md#%E5%85%B3%E4%BA%8E%E9%A2%84%E6%9C%9F%E5%BC%82%E5%B8%B8%E7%9A%84%E6%96%AD%E8%A8%80)

* #### [pytest fixture：易于理解的, 模块化, 可拓展](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md)
    * [将fixture作为函数参数](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#%E5%B0%86fixture%E4%BD%9C%E4%B8%BA%E5%87%BD%E6%95%B0%E5%8F%82%E6%95%B0)
    * [fixture:依赖注入的一个典型例子](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#fixture%E4%BE%9D%E8%B5%96%E6%B3%A8%E5%85%A5%E7%9A%84%E4%B8%80%E4%B8%AA%E5%85%B8%E5%9E%8B%E4%BE%8B%E5%AD%90)
    * [conftest.py:共享fixture函数](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [共享测试数据](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [范围：在类，模块或会话中的测试之间共享fixture实例](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [顺序：首先实例化范围更大的fixture](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [Fixture终止/执行teardown代码](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [Fixtures可以内省请求的测试上下文](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [fixtures工厂](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [fixtures参数化](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [使用带有参数化fixtures的标记](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [模块化：使用fixture函数中的fixtures](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [按照fixture实例自动将测试分组](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [使用类，模块或项目中的fixture](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [自动使用fixtures(xUnit setup on steroids)](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)
    * [覆盖各个级别的fixture](https://github.com/CHSherlock/pytest-zh-CN/blob/master/pytest%20fixture%EF%BC%9A%E6%98%93%E4%BA%8E%E7%90%86%E8%A7%A3%E7%9A%84%2C%20%E6%A8%A1%E5%9D%97%E5%8C%96%2C%20%E5%8F%AF%E6%8B%93%E5%B1%95.md#conftest-py%E5%85%B1%E4%BA%ABfixture%E5%87%BD%E6%95%B0)

* #### [使用属性标记测试函数](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%B1%9E%E6%80%A7%E6%A0%87%E8%AE%B0%E6%B5%8B%E8%AF%95%E5%87%BD%E6%95%B0.md)
    * [注册标记](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%B1%9E%E6%80%A7%E6%A0%87%E8%AE%B0%E6%B5%8B%E8%AF%95%E5%87%BD%E6%95%B0.md#%E6%B3%A8%E5%86%8C%E6%A0%87%E8%AE%B0)
    * [在未知标记上引发错误](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E4%BD%BF%E7%94%A8%E5%B1%9E%E6%80%A7%E6%A0%87%E8%AE%B0%E6%B5%8B%E8%AF%95%E5%87%BD%E6%95%B0.md#%E5%9C%A8%E6%9C%AA%E7%9F%A5%E6%A0%87%E8%AE%B0%E4%B8%8A%E5%BC%95%E5%8F%91%E9%94%99%E8%AF%AF)

* #### [猴子补丁/模拟模块和环境](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E6%88%96%E8%80%85%E6%A8%A1%E6%8B%9F%E6%A8%A1%E5%9D%97%E5%92%8C%E7%8E%AF%E5%A2%83.md)
    * [简单示例:猴子补丁函数](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E6%88%96%E8%80%85%E6%A8%A1%E6%8B%9F%E6%A8%A1%E5%9D%97%E5%92%8C%E7%8E%AF%E5%A2%83.md#%E7%AE%80%E5%8D%95%E7%A4%BA%E4%BE%8B%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E5%87%BD%E6%95%B0)
    * [猴子补丁返回的对象：构建模拟类](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E6%88%96%E8%80%85%E6%A8%A1%E6%8B%9F%E6%A8%A1%E5%9D%97%E5%92%8C%E7%8E%AF%E5%A2%83.md#%E7%AE%80%E5%8D%95%E7%A4%BA%E4%BE%8B%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E5%87%BD%E6%95%B0)
    * [全局补丁示例:防止"requests"从远程操作](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E6%88%96%E8%80%85%E6%A8%A1%E6%8B%9F%E6%A8%A1%E5%9D%97%E5%92%8C%E7%8E%AF%E5%A2%83.md#%E7%AE%80%E5%8D%95%E7%A4%BA%E4%BE%8B%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E5%87%BD%E6%95%B0)
    * [猴子补丁环境变量](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E6%88%96%E8%80%85%E6%A8%A1%E6%8B%9F%E6%A8%A1%E5%9D%97%E5%92%8C%E7%8E%AF%E5%A2%83.md#%E7%AE%80%E5%8D%95%E7%A4%BA%E4%BE%8B%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E5%87%BD%E6%95%B0)
    * [猴子补丁字典](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E6%88%96%E8%80%85%E6%A8%A1%E6%8B%9F%E6%A8%A1%E5%9D%97%E5%92%8C%E7%8E%AF%E5%A2%83.md#%E7%AE%80%E5%8D%95%E7%A4%BA%E4%BE%8B%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E5%87%BD%E6%95%B0)
    * [API参考资料](https://github.com/CHSherlock/pytest-zh-CN/blob/master/%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E6%88%96%E8%80%85%E6%A8%A1%E6%8B%9F%E6%A8%A1%E5%9D%97%E5%92%8C%E7%8E%AF%E5%A2%83.md#%E7%AE%80%E5%8D%95%E7%A4%BA%E4%BE%8B%E7%8C%B4%E5%AD%90%E8%A1%A5%E4%B8%81%E5%87%BD%E6%95%B0)

* #### [临时目录和文件](https://docs.pytest.org/en/latest/tmpdir.html)
    * [tmp路径夹具](https://docs.pytest.org/en/latest/tmpdir.html#the-tmp-path-fixture)
    * [tmp_path_factory夹具](https://docs.pytest.org/en/latest/tmpdir.html#the-tmp-path-factory-fixture)
    * [tmpdir夹具](https://docs.pytest.org/en/latest/tmpdir.html#the-tmpdir-fixture)
    * [tmpdir_factory夹具](https://docs.pytest.org/en/latest/tmpdir.html#the-tmpdir-factory-fixture)
    * [默认的基本临时目录](https://docs.pytest.org/en/latest/tmpdir.html#the-default-base-temporary-directory)

* #### [捕获标准输出/标准错误输出](https://docs.pytest.org/en/latest/capture.html)
    * [默认的标准输出/标准错误/标准输入捕获行为](https://docs.pytest.org/en/latest/capture.html#default-stdout-stderr-stdin-capturing-behaviour)
    * [设置捕获方法或禁用捕获](https://docs.pytest.org/en/latest/capture.html#setting-capturing-methods-or-disabling-capturing)
    * [使用print语句进行调试](https://docs.pytest.org/en/latest/capture.html#using-print-statements-for-debugging)
    * [访问从测试函数捕获的输出](https://docs.pytest.org/en/latest/capture.html#accessing-captured-output-from-a-test-function)

* #### [警告捕获](https://docs.pytest.org/en/latest/warnings.html)
    * [@pytest.mark.filterwarnings](https://docs.pytest.org/en/latest/warnings.html#pytest-mark-filterwarnings)
    * [禁用警告摘要](https://docs.pytest.org/en/latest/warnings.html#disabling-warnings-summary)
    * [完全禁用警告捕获](https://docs.pytest.org/en/latest/warnings.html#disabling-warning-capture-entirely)
    * [弃用警告和待处理弃用警告](https://docs.pytest.org/en/latest/warnings.html#deprecationwarning-and-pendingdeprecationwarning)
    * [确保代码触发弃用警告](https://docs.pytest.org/en/latest/warnings.html#ensuring-code-triggers-a-deprecation-warning)
    * [使用warn函数断言警告](https://docs.pytest.org/en/latest/warnings.html#warns)
    * [记录警告](https://docs.pytest.org/en/latest/warnings.html#recwarn)
    * [自定义失败消息](https://docs.pytest.org/en/latest/warnings.html#custom-failure-messages)
    * [pytest内部警告](https://docs.pytest.org/en/latest/warnings.html#internal-pytest-warnings)

* #### [Doctest集成了模块和测试文件](https://docs.pytest.org/en/latest/doctest.html)
    * [编码](https://docs.pytest.org/en/latest/doctest.html#encoding)
    * [使用“ doctest”选项](https://docs.pytest.org/en/latest/doctest.html#using-doctest-options)
    * [失败后继续测试](https://docs.pytest.org/en/latest/doctest.html#continue-on-failure)
    * [输出格式](https://docs.pytest.org/en/latest/doctest.html#output-format)
    * [pytest-specific 特性](https://docs.pytest.org/en/latest/doctest.html#pytest-specific-features)

* #### [Skip and xfail: 处理不能成功的测试](https://docs.pytest.org/en/latest/skipping.html)
    * [跳过测试函数](https://docs.pytest.org/en/latest/skipping.html#skipping-test-functions)
    * [XFail:将测试函数标记为预期会失败](https://docs.pytest.org/en/latest/skipping.html#xfail-mark-test-functions-as-expected-to-fail)
    * [通过参数化Skip/xfail](https://docs.pytest.org/en/latest/skipping.html#skip-xfail-with-parametrize)

* #### [参数化fixtures和测试函数](https://docs.pytest.org/en/latest/parametrize.html)
    * [@pytest.mark.parametrize:参数化测试函数](https://docs.pytest.org/en/latest/parametrize.html#pytest-mark-parametrize-parametrizing-test-functions)
    * [pytest_generate_tests基本示例](https://docs.pytest.org/en/latest/parametrize.html#basic-pytest-generate-tests-example)
    * [更多例子](https://docs.pytest.org/en/latest/parametrize.html#more-examples)

* #### [缓存：使用交叉测试运行状态](https://docs.pytest.org/en/latest/cache.html)
    * [使用](https://docs.pytest.org/en/latest/cache.html#usage)
    * [只重新运行失败的案例或先运行失败的案例](https://docs.pytest.org/en/latest/cache.html#rerunning-only-failures-or-failures-first)
    * [在最后一次运行中没有测试失败时的行为](https://docs.pytest.org/en/latest/cache.html#behavior-when-no-tests-failed-in-the-last-run)
    * [新的config.cache对象](https://docs.pytest.org/en/latest/cache.html#the-new-config-cache-object)
    * [检查缓存内容](https://docs.pytest.org/en/latest/cache.html#inspecting-cache-content)
    * [清除缓存内容](https://docs.pytest.org/en/latest/cache.html#clearing-cache-content)
    * [逐步回归分析](https://docs.pytest.org/en/latest/cache.html#stepwise)

* #### [unittest.TestCase支持](https://docs.pytest.org/en/latest/unittest.html)
    * [开箱即用的好处](https://docs.pytest.org/en/latest/unittest.html#benefits-out-of-the-box)
    * [pytest在unittest.TestCase子类中的features](https://docs.pytest.org/en/latest/unittest.html#pytest-features-in-unittest-testcase-subclasses)
    * [使用标记，将pytest features混合到unittest.TestCase子类中](https://docs.pytest.org/en/latest/unittest.html#mixing-pytest-fixtures-into-unittest-testcase-subclasses-using-marks)
    * [自动使用features和访问其它features](https://docs.pytest.org/en/latest/unittest.html#using-autouse-fixtures-and-accessing-other-fixtures)

* #### [运行为nose编写的测试](https://docs.pytest.org/en/latest/nose.html)
    * [使用](https://docs.pytest.org/en/latest/nose.html#usage)
    * [支持的nose习惯用法](https://docs.pytest.org/en/latest/nose.html#supported-nose-idioms)
    * [不支持的习惯用法/已知问题](https://docs.pytest.org/en/latest/nose.html#unsupported-idioms-known-issues)

* #### [经典的xunit-style的设置](https://docs.pytest.org/en/latest/xunit_setup.html)
    * [模块级别的安装/拆卸](https://docs.pytest.org/en/latest/xunit_setup.html#module-level-setup-teardown)
    * [类级别的安装/拆卸](https://docs.pytest.org/en/latest/xunit_setup.html#class-level-setup-teardown)
    * [方法和函数级别的安装/拆卸](https://docs.pytest.org/en/latest/xunit_setup.html#method-and-function-level-setup-teardown)

* #### [安装和使用插件](https://docs.pytest.org/en/latest/plugins.html)
    * [在测试模块或者conftest文件中要求/加载插件](https://docs.pytest.org/en/latest/plugins.html#requiring-loading-plugins-in-a-test-module-or-conftest-file)
    * [找出哪些插件处于活动状态](https://docs.pytest.org/en/latest/plugins.html#finding-out-which-plugins-are-active)
    * [通过名称停用/注销插件](https://docs.pytest.org/en/latest/plugins.html#deactivating-unregistering-a-plugin-by-name)

* #### [编写插件](https://docs.pytest.org/en/latest/writing_plugins.html)
    * [工具启动时的插件发现顺序](https://docs.pytest.org/en/latest/writing_plugins.html#plugin-discovery-order-at-tool-startup)
    * [conftest.py:本地per-directory插件](https://docs.pytest.org/en/latest/writing_plugins.html#conftest-py-local-per-directory-plugins)
    * [编写自己的插件](https://docs.pytest.org/en/latest/writing_plugins.html#writing-your-own-plugin)
    * [使您的插件可以被其他人安装](https://docs.pytest.org/en/latest/writing_plugins.html#making-your-plugin-installable-by-others)
    * [断言重写](https://docs.pytest.org/en/latest/writing_plugins.html#assertion-rewriting)
    * [在测试模块或者conftest文件中要求/加载插件](https://docs.pytest.org/en/latest/writing_plugins.html#requiring-loading-plugins-in-a-test-module-or-conftest-file)
    * [通过名称访问另一个插件](https://docs.pytest.org/en/latest/writing_plugins.html#accessing-another-plugin-by-name)
    * [注册自定义标记](https://docs.pytest.org/en/latest/writing_plugins.html#registering-custom-markers)
    * [测试插件](https://docs.pytest.org/en/latest/writing_plugins.html#testing-plugins)

* #### [编写钩子函数](https://docs.pytest.org/en/latest/writing_plugins.html#writing-hook-functions)
    * [钩子函数验证和执行](https://docs.pytest.org/en/latest/writing_plugins.html#hook-function-validation-and-execution)
    * [firstresult：在第一个非None结果处停止](https://docs.pytest.org/en/latest/writing_plugins.html#firstresult-stop-at-first-non-none-result)
    * [hookwrapper：围绕其他钩子执行](https://docs.pytest.org/en/latest/writing_plugins.html#hookwrapper-executing-around-other-hooks)
    * [钩子函数排序/调用的例子](https://docs.pytest.org/en/latest/writing_plugins.html#hook-function-ordering-call-example)
    * [声明新的钩子](https://docs.pytest.org/en/latest/writing_plugins.html#declaring-new-hooks)
    * [使用pytest_addoption中的钩子](https://docs.pytest.org/en/latest/writing_plugins.html#using-hooks-in-pytest-addoption)
    * [可选地使用来自第三方插件的钩子](https://docs.pytest.org/en/latest/writing_plugins.html#optionally-using-hooks-from-3rd-party-plugins)

* #### [日志](https://docs.pytest.org/en/latest/logging.html)
    * [caplog fixture](https://docs.pytest.org/en/latest/logging.html#caplog-fixture)
    * [实时日志](https://docs.pytest.org/en/latest/logging.html#live-logs)
    * [发布说明](https://docs.pytest.org/en/latest/logging.html#release-notes)
    * [pytest 3.4中不兼容的更改](https://docs.pytest.org/en/latest/logging.html#incompatible-changes-in-pytest-3-4)

* #### [API参考](https://docs.pytest.org/en/latest/reference.html)
    * [函数(Functions)](https://docs.pytest.org/en/latest/reference.html#functions)
    * [标记(Marks)](https://docs.pytest.org/en/latest/reference.html#marks)
    * [夹具(Fixtures)](https://docs.pytest.org/en/latest/reference.html#fixtures)
    * [钩子(Hooks)](https://docs.pytest.org/en/latest/reference.html#hooks)
    * [对象(Objects)](https://docs.pytest.org/en/latest/reference.html#objects)
    * [特殊变量(Special Variables)](https://docs.pytest.org/en/latest/reference.html#special-variables)
    * [环境变量(Environment Variables)](https://docs.pytest.org/en/latest/reference.html#environment-variables)
    * [异常(Exceptions)](https://docs.pytest.org/en/latest/reference.html#exceptions)
    * [配置选项(Configuration Options)](https://docs.pytest.org/en/latest/reference.html#configuration-options)

* #### [良好的集成实践](https://docs.pytest.org/en/latest/goodpractices.html)
    * [用pip安装软件包](https://docs.pytest.org/en/latest/goodpractices.html#install-package-with-pip)
    * [Python测试发现的约定](https://docs.pytest.org/en/latest/goodpractices.html#conventions-for-python-test-discovery)
    * [选择测试布局/导入规则](https://docs.pytest.org/en/latest/goodpractices.html#choosing-a-test-layout-import-rules)
    * [tox](https://docs.pytest.org/en/latest/goodpractices.html#tox)

* #### [同等条件下有时失败,有时成功的测试(Flaky tests)](https://docs.pytest.org/en/latest/flaky.html)
    * [为什么flaky tests是一个问题](https://docs.pytest.org/en/latest/flaky.html#why-flaky-tests-are-a-problem)
    * [潜在根源](https://docs.pytest.org/en/latest/flaky.html#potential-root-causes)
    * [pytest特性](https://docs.pytest.org/en/latest/flaky.html#pytest-features)
    * [其他的一般策略](https://docs.pytest.org/en/latest/flaky.html#other-general-strategies)
    * [研究](https://docs.pytest.org/en/latest/flaky.html#research)
    * [资源](https://docs.pytest.org/en/latest/flaky.html#resources)

* #### [pytest导入机制和sys.path/PYTHONPATH](https://docs.pytest.org/en/latest/pythonpath.html)
    * [包中的测试模块/ conftest.py文件](https://docs.pytest.org/en/latest/pythonpath.html)
    * [独立的测试模块/ conftest.py文件](https://docs.pytest.org/en/latest/pythonpath.html#standalone-test-modules-conftest-py-files)
    * [调用pytest与python -m pytest](https://docs.pytest.org/en/latest/pythonpath.html#invoking-pytest-versus-python-m-pytest)

* #### [配置](https://docs.pytest.org/en/latest/customize.html)
    * [命令行选项和配置文件设置](https://docs.pytest.org/en/latest/customize.html#command-line-options-and-configuration-file-settings)
    * [初始化：决定根目录和初始化文件](https://docs.pytest.org/en/latest/customize.html#initialization-determining-rootdir-and-inifile)
    * [如何更改命令行默认选项](https://docs.pytest.org/en/latest/customize.html#adding-default-options)
    * [内置配置文件选项](https://docs.pytest.org/en/latest/customize.html#builtin-configuration-file-options)

* #### [示例和自定义技巧]()
    * [用pytest演示Python失败报告](https://docs.pytest.org/en/latest/example/reportingdemo.html)
    * [基本模式和示例](https://docs.pytest.org/en/latest/example/simple.html)
    * [参数化测试](https://docs.pytest.org/en/latest/example/parametrize.html)
    * [使用自定义标记](https://docs.pytest.org/en/latest/example/markers.html)
    * [一个可以查看所有收集到的测试的session-fixtures](https://docs.pytest.org/en/latest/example/special.html)
    * [变更标准(Python)测试发现](https://docs.pytest.org/en/latest/example/pythoncollection.html)
    * [使用非python测试](https://docs.pytest.org/en/latest/example/nonpython.html)

* #### [Setting up bash completion](https://docs.pytest.org/en/latest/bash-completion.html)
* #### [一些问题和疑问](https://docs.pytest.org/en/latest/faq.html)
    * [关于命名,nose测试,许可和魔术](https://docs.pytest.org/en/latest/faq.html#on-naming-nosetests-licensing-and-magic)
    * [pytest fixtures,参数化测试](https://docs.pytest.org/en/latest/faq.html#pytest-fixtures-parametrized-tests)
    * [pytest与其他软件包的交互](https://docs.pytest.org/en/latest/faq.html#pytest-interaction-with-other-packages)

* #### [向后兼容策略](https://docs.pytest.org/en/latest/backwards-compatibility.html)
* #### [历史](https://docs.pytest.org/en/latest/backwards-compatibility.html#history)
    * [在6.0版本之前,我们的立场是专注于平稳过渡](https://docs.pytest.org/en/latest/backwards-compatibility.html#focus-primary-on-smooth-transition-stance-pre-6-0)

* #### [弃用和移除的功能](https://docs.pytest.org/en/latest/backwards-compatibility.html#focus-primary-on-smooth-transition-stance-pre-6-0)
    * [弃用的功能](https://docs.pytest.org/en/latest/deprecations.html#deprecated-features)
    * [移除的功能](https://docs.pytest.org/en/latest/deprecations.html#removed-features)

* #### [支持Python 2.7和3.4](https://docs.pytest.org/en/latest/py27-py34-deprecation.html)
    * [这对一般用户意味着什么](https://docs.pytest.org/en/latest/py27-py34-deprecation.html#what-this-means-for-general-users)
    * [维护4.6.X版本](https://docs.pytest.org/en/latest/py27-py34-deprecation.html)

* #### [如何贡献](https://docs.pytest.org/en/latest/contributing.html)
    * [功能建议和反馈](https://docs.pytest.org/en/latest/contributing.html#feature-requests-and-feedback)
    * [报告错误](https://docs.pytest.org/en/latest/contributing.html#report-bugs)
    * [修正错误](https://docs.pytest.org/en/latest/contributing.html#fix-bugs)
    * [实现功能](https://docs.pytest.org/en/latest/contributing.html#implement-features)
    * [编写文档](https://docs.pytest.org/en/latest/contributing.html#submitting-plugins-to-pytest-dev)
    * [提交插件到pytest-dev](https://docs.pytest.org/en/latest/contributing.html#submitting-plugins-to-pytest-dev)
    * [做好拉取请求的准备](https://docs.pytest.org/en/latest/contributing.html#preparing-pull-requests)
    * [编写测试](https://docs.pytest.org/en/latest/contributing.html#writing-tests)
    * [加入开发团队](https://docs.pytest.org/en/latest/contributing.html#joining-the-development-team)

* #### [开发指南](https://docs.pytest.org/en/latest/development_guide.html)
    * [代码样式](https://docs.pytest.org/en/latest/development_guide.html#code-style)
    * [分支](https://docs.pytest.org/en/latest/development_guide.html#branches)
    * [问题](https://docs.pytest.org/en/latest/development_guide.html#issues)
    * [发布程序](https://docs.pytest.org/en/latest/development_guide.html#release-procedure)

* #### [赞助者](https://docs.pytest.org/en/latest/sponsor.html)
    * [OpenCollective](https://docs.pytest.org/en/latest/sponsor.html#opencollective)

* #### [面向企业的pytest](https://docs.pytest.org/en/latest/tidelift.html)

* #### [许可证明](https://docs.pytest.org/en/latest/license.html)

* #### [联系渠道](https://docs.pytest.org/en/latest/contact.html)

* #### [历史记录](https://docs.pytest.org/en/latest/historical-notes.html)
    * [标记修改和迭代](https://docs.pytest.org/en/latest/historical-notes.html#marker-revamp-and-iteration)
    * [核心缓存插件](https://docs.pytest.org/en/latest/historical-notes.html#cache-plugin-integrated-into-the-core)
    * [funcargs and pytest_funcarg__](https://docs.pytest.org/en/latest/historical-notes.html#funcargs-and-pytest-funcarg)
    * [@pytest.yield_fixture装饰器](https://docs.pytest.org/en/latest/historical-notes.html#pytest-yield-fixture-decorator)
    * [在setup.cfg中的pytest标头](https://docs.pytest.org/en/latest/historical-notes.html#pytest-header-in-setup-cfg)
    * [将标记应用于@ pytest.mark.parametrize参数](https://docs.pytest.org/en/latest/historical-notes.html#applying-marks-to-pytest-mark-parametrize-parameters)
    * [@pytest.mark.parametrize将参数名称指定为元组](https://docs.pytest.org/en/latest/historical-notes.html#pytest-mark-parametrize-argument-names-as-a-tuple)
    * [设置：现在是“auto fixture”](https://docs.pytest.org/en/latest/historical-notes.html#setup-is-now-an-autouse-fixture)
    * [条件是字符串而不是布尔值](https://docs.pytest.org/en/latest/historical-notes.html#conditions-as-strings-instead-of-booleans)
    * [pytest.set_trace()](https://docs.pytest.org/en/latest/historical-notes.html#pytest-set-trace)
    * [“兼容”属性](https://docs.pytest.org/en/latest/historical-notes.html#compat-properties)

* #### [讲座和教程](https://docs.pytest.org/en/latest/talks.html)
    * [书](https://docs.pytest.org/en/latest/talks.html#books)
    * [讲座和博客文章](https://docs.pytest.org/en/latest/talks.html#talks-and-blog-postings)

* #### [工程实例](https://docs.pytest.org/en/latest/projects.html)
    * [一些使用pytest的组织](https://docs.pytest.org/en/latest/projects.html#some-organisations-using-pytest)

* #### [发布公告](https://docs.pytest.org/en/latest/announce/index.html)
