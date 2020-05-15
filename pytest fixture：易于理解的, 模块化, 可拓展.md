[软件测试夹具](https://en.wikipedia.org/wiki/Test_fixture#Software) 初始化测试函数。它们提供了固定的基准，因此测试可以可靠地执行并产生一致的、可重复的结果。初始化可以设置服务、状态或其他操作环境。测试函数通过参数访问它们;对于测试函数使用的每个fixture，在测试函数的定义中通常都有一个参数(以fixture命名)。

pytest fixture相对于经典的xUnit样式的设置/拆卸功能进行了重大改良：

* fixture具有明确的名称，并通过从测试函数、模块、类或整个项目中声明它们的使用来激活。
* fixture以模块化的方式实现，因为每个fixture名称都触发一个fixture函数，而这个fixture函数本身可以使用其他fixture。
* fixture管理的范围从简单的单元扩展到复杂的功能测试，允许根据配置和组件选项对fixture和测试进行参数化，或者跨函数、类、模块或整个测试会话范围重复使用fixture。

另外，pytest继续支持经典的xunit风格的设置。您可以混合使用这两种风格，根据自己的喜好从经典风格逐渐过渡到新风格。您也可以从现有的[unittest.TestCase style](https://docs.pytest.org/en/latest/unittest.html#unittest-testcase)或[基于nose](https://docs.pytest.org/en/latest/nose.html#nosestyle)的项目开始。

[Fixtures](https://docs.pytest.org/en/latest/reference.html#fixtures-api) 是使用[@pytest.fixture](https://docs.pytest.org/en/latest/reference.html#pytest-fixture-api)装饰器定义的，[点此查看详情](https://docs.pytest.org/en/latest/fixture.html#funcargs)。Pytest有一些有用的内置fixtures，在这里列出以供参考：

&nbsp; &nbsp; &nbsp; &nbsp; [capfd](https://docs.pytest.org/en/latest/reference.html#std:fixture-capfd)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 捕获，作为文本，输出到文件描述符`1`和`2`。

&nbsp; &nbsp; &nbsp; &nbsp; [capfdbinary](https://docs.pytest.org/en/latest/reference.html#std:fixture-capfdbinary)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 捕获，作为字节，输出到文件描述符`1`和`2`。

&nbsp; &nbsp; &nbsp; &nbsp; [caplog](https://docs.pytest.org/en/latest/reference.html#std:fixture-caplog)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 控制日志记录和访问日志条目。

&nbsp; &nbsp; &nbsp; &nbsp; [capsys](https://docs.pytest.org/en/latest/reference.html#std:fixture-capsys)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 捕获，作为文本，输出到`sys.stdout`和`sys.stderr`。

&nbsp; &nbsp; &nbsp; &nbsp; [capsysbinary](https://docs.pytest.org/en/latest/reference.html#std:fixture-capsysbinary)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 捕获，作为字节，输出到`sys.stdout`和`sys.stderr`。

&nbsp; &nbsp; &nbsp; &nbsp; [cache](https://docs.pytest.org/en/latest/reference.html#std:fixture-cache)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 在pytest运行期间存储和检索值。

&nbsp; &nbsp; &nbsp; &nbsp; [doctest_namespace](https://docs.pytest.org/en/latest/reference.html#std:fixture-doctest_namespace)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 提供一个注入docstests命名空间的字典。

&nbsp; &nbsp; &nbsp; &nbsp; [monkeypatch](https://docs.pytest.org/en/latest/reference.html#std:fixture-monkeypatch)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; 临时修改类，函数，字典，`os.environ`和其他对象。

&nbsp; &nbsp; &nbsp; &nbsp; [record_property](https://docs.pytest.org/en/latest/reference.html#std:fixture-record_property)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  向测试添加额外的属性。

&nbsp; &nbsp; &nbsp; &nbsp; [record_testsuite_property](https://docs.pytest.org/en/latest/reference.html#std:fixture-record_testsuite_property)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  向测试套件中添加额外的属性。

&nbsp; &nbsp; &nbsp; &nbsp; [recwarn](https://docs.pytest.org/en/latest/reference.html#std:fixture-recwarn)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  记录测试函数发出的警告。

&nbsp; &nbsp; &nbsp; &nbsp; [request](https://docs.pytest.org/en/latest/reference.html#std:fixture-request)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  提供有关正在执行的测试函数的信息。

&nbsp; &nbsp; &nbsp; &nbsp; [testdir](https://docs.pytest.org/en/latest/reference.html#std:fixture-testdir)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  提供一个临时测试目录来帮助运行和测试pytest插件。

&nbsp; &nbsp; &nbsp; &nbsp; [tmp_path](https://docs.pytest.org/en/latest/reference.html#std:fixture-tmp_path)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  提供一个[pathlib.Path](https://docs.python.org/3/library/pathlib.html#pathlib.Path)对象指向一个临时目录，该目录对于每个测试函数都是惟一的。

&nbsp; &nbsp; &nbsp; &nbsp; [tmp_path_factory](https://docs.pytest.org/en/latest/reference.html#std:fixture-tmp_path_factory)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  创建会话范围的临时目录并返回[pathlib.Path](https://docs.python.org/3/library/pathlib.html#pathlib.Path)对象。

&nbsp; &nbsp; &nbsp; &nbsp; [tmpdir](https://docs.pytest.org/en/latest/reference.html#std:fixture-tmpdir)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  提供一个py.path.local对象指向一个临时目录，该目录对于每个测试函数都是惟一的;替换为[tmp_path](https://docs.pytest.org/en/latest/reference.html#std:fixture-tmp_path).

&nbsp; &nbsp; &nbsp; &nbsp; [tmpdir_factory](https://docs.pytest.org/en/latest/reference.html#std:fixture-tmpdir_factory)  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;  建会话范围的临时目录并返回py.path.local对象； 由[tmp_path_factory](https://docs.pytest.org/en/latest/reference.html#std:fixture-tmp_path_factory)代替。

#### 将fixture作为函数参数

测试函数可以通过将fixture对象命名为输入参数来接收它们。
对于每个参数名称，具有该名称的Fixture函数将提供Fixture对象。Fixture函数是通过将它们标记为@pytest.fixture来注册的。让我们来看一个简单的自包含测试模块，其中包含一个fixture和一个使用它的测试函数:

    # content of ./test_smtpsimple.py
    import pytest
    

    @pytest.fixture
    def smtp_connection():
        import smtplib

        return smtplib.SMTP("smtp.gmail.com", 587, timeout=5)
    

    def test_ehlo(smtp_connection):
        response, msg = smtp_connection.ehlo()
        assert response == 250
        assert 0  # for demo purposes

这里，`test_ehlo`需要`smtp_connection` fixture的值。pytest将发现并调用@pytest.fixture标识的`smtp_connection`fixture函数。 运行测试如下所示：

    $ pytest test_smtpsimple.py
    =========================== test session starts ============================
    platform linux -- Python 3.x.y, pytest-5.x.y, py-1.x.y, pluggy-0.x.y
    cachedir: $PYTHON_PREFIX/.pytest_cache
    rootdir: $REGENDOC_TMPDIR
    collected 1 item

    test_smtpsimple.py F                                                 [100%]

    ================================= FAILURES =================================
    ________________________________ test_ehlo _________________________________

    smtp_connection = <smtplib.SMTP object at 0xdeadbeef>

        def test_ehlo(smtp_connection):
            response, msg = smtp_connection.ehlo()
            assert response == 250
    >       assert 0  # for demo purposes
    E       assert 0

    test_smtpsimple.py:14: AssertionError
    ========================= short test summary info ==========================
    FAILED test_smtpsimple.py::test_ehlo - assert 0
    ============================ 1 failed in 0.12s =============================

在失败回溯中，我们看到测试函数是通过`smtp_connection`参数调用的，该参数是由fixture函数创建的`smtplib.SMTP()`实例。测试函数在故意设置的`assert 0`上失败。下面是pytest以这种方式调用测试函数所使用的确切协议:

1. pytest由于test_前缀而[找到](https://docs.pytest.org/en/latest/goodpractices.html#test-discovery)了test_ehlo。 测试函数需要一个名为`smtp_connection`的函数参数。通过查找名为`smtp_connection`的带有fixture标记的函数，可以找到匹配的fixture函数。
2. 调用`smtp connection()`创建实例。
3. `test_ehlo(<smtp_connection实例>)`被调用，并且在测试函数的最后一行中失败。

><font size = 5>注意：</font>  
>
>您可以随时发出：   
>
>&nbsp; &nbsp; pytest --fixtures test_simplefactory.py  
>
>以查看可用的fixture(只有添加-v选项时才会显示具有前导_的fixture)。

#### fixture:依赖注入的一个典型例子

fixture允许测试函数轻松地接收和处理特定的预先初始化的应用程序对象，而不需要关心导入/设置/清理的细节。这是[依赖项注入](https://en.wikipedia.org/wiki/Dependency_injection)的一个典型示例，其中fixture函数充当注入器的角色，测试函数是fixture对象的使用者。

#### conftest .py:共享fixture函数

如果在实现测试的过程中，您意识到需要使用来自多个测试文件的fixture函数，那么可以将其移动到`conftest.py`文件中。您不需要导入要在测试中使用的fixture, pytest会自动发现它。fixture函数的发现从测试类开始，然后是测试模块，然后是conftest.py文件，最后是构建插件和第三方插件。

您还可以使用`conftest.py`文件来实现 [每个目录的本地插件](https://docs.pytest.org/en/latest/writing_plugins.html#conftest-py-plugins)。

#### 共享测试数据

如果您想要使来自文件的测试数据对您的测试可用，一种好的方法是将这些数据加载到一个fixture中，以供您的测试使用。这就利用了pytest的自动缓存机制。

另一种好的方法是在`tests`文件夹中添加数据文件。还有一些社区插件可以帮助管理这方面的测试，例如[pytest-datadir](https://pypi.org/project/pytest-datadir/)和[pytest-datafile](https://pypi.org/project/pytest-datafiles/)。

#### 范围：在类，模块或会话中的测试之间共享fixture实例

需要网络访问的fixture依赖于连接性，创建这些fixture通常非常耗时。扩展前面的示例，我们可以在@pytest.fixture调用中添加`scope=“module”`参数，以使装饰的`smtp_connection` fixture函数仅在每个测试模块中调用一次（默认是每个测试函数调用一次）。因此，测试模块中的多个测试函数将各自接收相同的`smtp_connection` fixture实例，从而节省时间。作用域的可能值是:函数、类、模块、包或会话。

下一个示例将fixture函数放入一个单独的`conftest.py`文件中，以便来自目录中的多个测试模块的测试可以访问fixture函数:

    # content of conftest.py
    import pytest
    import smtplib
    

    @pytest.fixture(scope="module")
    def smtp_connection():
        return smtplib.SMTP("smtp.gmail.com", 587, timeout=5)

fixture的名称仍然是`smtp_connection`，您可以通过将`smtp_connection`的名称作为输入参数列在任何测试或fixture函数中(`conftest.py`所在的目录中或目录下)来访问它的结果。

    # content of test_module.py
    

    def test_ehlo(smtp_connection):
        response, msg = smtp_connection.ehlo()
        assert response == 250
        assert b"smtp.gmail.com" in msg
        assert 0  # for demo purposes
    

    def test_noop(smtp_connection):
        response, msg = smtp_connection.noop()
        assert response == 250
        assert 0  # for demo purposes

我们故意插入失败的assert 0语句，以检查发生了什么，现在可以运行测试了：

    $ pytest test_module.py
    =========================== test session starts ============================
    platform linux -- Python 3.x.y, pytest-5.x.y, py-1.x.y, pluggy-0.x.y
    cachedir: $PYTHON_PREFIX/.pytest_cache
    rootdir: $REGENDOC_TMPDIR
    collected 2 items

    test_module.py FF                                                    [100%]

    ================================= FAILURES =================================
    ________________________________ test_ehlo _________________________________

    smtp_connection = <smtplib.SMTP object at 0xdeadbeef>

        def test_ehlo(smtp_connection):
            response, msg = smtp_connection.ehlo()
            assert response == 250
            assert b"smtp.gmail.com" in msg
    >       assert 0  # for demo purposes
    E       assert 0

    test_module.py:7: AssertionError
    ________________________________ test_noop _________________________________

    smtp_connection = <smtplib.SMTP object at 0xdeadbeef>

        def test_noop(smtp_connection):
            response, msg = smtp_connection.noop()
            assert response == 250
    >       assert 0  # for demo purposes
    E       assert 0

    test_module.py:13: AssertionError
    ========================= short test summary info ==========================
    FAILED test_module.py::test_ehlo - assert 0
    FAILED test_module.py::test_noop - assert 0
    ============================ 2 failed in 0.12s =============================

您可以看到两个`assert0`失败，更重要的是，您还可以看到相同的(模块作用域)`smtp_connection`对象被传递到两个测试函数中，因为pytest在回溯中显示了传入的参数值。结果，使用`smtp_connection`的两个测试函数的运行速度与单个函数一样快，因为它们重用了同一实例。如果您决定宁愿要一个会话范围的`smtp_connection`实例，您可以简单地声明它:

    @pytest.fixture(scope="session")
    def smtp_connection():
        # the returned fixture value will be shared for
        # all tests needing it
        ...

最后，类作用域将为每个测试类调用一次fixture。

><font size=5>注意：</font>  
>Pytest每次只缓存一个fixture实例。这意味着当使用参数化的fixture时，pytest可以在给定的范围内多次调用fixture。

##### 包的作用域（实验性）

在pytest 3.7中已经介绍了包的作用域。在包中最后一次测试结束时，包的作用域fixture也会确定下来。

><font size=5>警告：</font>  
这个功能被认为是实验性的，如果在这个功能得到更广泛的应用后，发现了隐藏的缺陷或严重的问题，那么在未来的版本中这个功能可能会被删除。

##### 动态作用域

版本5.2中的新功能。

在某些情况下，您可能希望在不更改代码的情况下更改fixture的范围。为此，请将可调用对象传递给`作用域`。可调用对象必须返回一个具有有效作用域的字符串，并且只执行一次——在fixture定义期间。将使用两个关键字参数来调用它——`fixture_name`作为字符串，`config`作为配置对象。  

这在处理需要设置时间的fixture(比如生成docker容器)时特别有用。您可以使用命令行参数来控制不同环境下生成的容器的作用域。 请参见下面的示例。

    def determine_scope(fixture_name, config):
        if config.getoption("--keep-containers", None):
            return "session"
        return "function"
    

    @pytest.fixture(scope=determine_scope)
    def docker_container():
        yield spawn_container()

#### 顺序：首先实例化范围更大的fixture

在对fixture的函数请求中，较高作用域的fixture（例如`会话`）会比较低作用域的fixture（例如`fixture`或`类`）先实例化。相同作用域的fixture的相对顺序遵循测试函数中声明的顺序，并遵循fixture之间的依赖关系。自动使用的fixture将在明确使用的fixture之前实例化。

思考下面的代码：

    import pytest

    # fixtures documentation order example
    order = []
    

    @pytest.fixture(scope="session")
    def s1():
        order.append("s1")
    

    @pytest.fixture(scope="module")
    def m1():
        order.append("m1")
    

    @pytest.fixture
    def f1(f3):
        order.append("f1")
    

    @pytest.fixture
    def f3():
        order.append("f3")
    

    @pytest.fixture(autouse=True)
    def a1():
        order.append("a1")
    

    @pytest.fixture
    def f2():
        order.append("f2")
    

    def test_order(f1, m1, f2, s1):
        assert order == ["s1", "m1", "a1", "f3", "f1", "f2"]

`test_order`请求的fixtures将按照以下顺序实例化:

1. `s1`：是作用域最高的fixture(`会话`)。
2. `m1`：是第二个作用域最高的fixture(`模块`)。
3. `a1`：是一个函数范围的自动使用fixture:它将在同一范围内的其他fixtures之前实例化。
4. `f3`：是一个函数范围的fixture，f1需要时：此时需要实例化。
5. `f1`：是test_order参数列表中的第一个作用域为函数的fixture。
6. `f2`：是test_order参数列表中最后一个作用域为函数的fixture。

#### Fixture终止/执行teardown代码

当fixture超出作用域时，pytest支持执行fixture特定的终结代码。通过使用`yield`语句而不是`return`, yield语句之后的所有代码都作为teardown代码:

    # content of conftest.py

    import smtplib
    import pytest
    

    @pytest.fixture(scope="module")
    def smtp_connection():
        smtp_connection = smtplib.SMTP("smtp.gmail.com", 587, timeout=5)
        yield smtp_connection  # provide the fixture value
        print("teardown smtp")
        smtp_connection.close()

不管测试的异常状态如何，`print`和`smtp.close()`语句将在模块中的最后一个测试完成时执行。

让我们执行它：

    $ pytest -s -q --tb=no
    FFteardown smtp

    ========================= short test summary info ==========================
    FAILED test_module.py::test_ehlo - assert 0
    FAILED test_module.py::test_noop - assert 0
    2 failed in 0.12s

我们看到`smtp_connection`实例在两个测试完成执行后完成。注意，如果我们用`scope='function'`修饰fixture函数，那么fixture的设置和清除将在每次测试前后进行。在这两种情况下，测试模块本身都不需要更改或了解这些fixture设置细节。

注意，我们还可以无缝地将`yield`语法与`with`语句一起使用:

    # content of test_yield2.py

    import smtplib
    import pytest
    

    @pytest.fixture(scope="module")
    def smtp_connection():
        with smtplib.SMTP("smtp.gmail.com", 587, timeout=5) as smtp_connection:
            yield smtp_connection  # 提供fixture的值

`smtp_connection`连接将在测试执行完成后关闭，因为当`with`语句结束时，`smtp_connection`对象会自动关闭。

无论fixture设置代码是否引发异常，contextlib.ExitStack上下文管理终结器总是会被调用。这对于正确关闭fixture创建的所有资源非常方便，即使他们中的一个没有创建/获得资源:

    # content of test_yield3.py

    import contextlib

    import pytest
    

    @contextlib.contextmanager
    def connect(port):
        ...  # create connection
        yield
        ...  # close connection
    

    @pytest.fixture
    def equipments():
        with contextlib.ExitStack() as stack:
            yield [stack.enter_context(connect(port)) for port in ("C1", "C3", "C28")]

在上面的例子中，如果`“C28”`异常失败，`“C1”`和`“C3”`仍然会被正确关闭。

注意，如果在设置代码期间(`yield`关键字之前)发生异常，那么将不会调用teardown代码(`yield`之后)。

执行teardown代码的另一个选择是使用 [request-context](https://docs.pytest.org/en/latest/fixture.html#request-context) 对象的`addfinalizer`方法来注册终结函数。

下面是`smtp_connection` fixture更改为使用`addfinalizer`进行清理的情况:

    # content of conftest.py
    import smtplib
    import pytest
    

    @pytest.fixture(scope="module")
    def smtp_connection(request):
        smtp_connection = smtplib.SMTP("smtp.gmail.com", 587, timeout=5)

        def fin():
            print("teardown smtp_connection")
            smtp_connection.close()

        request.addfinalizer(fin)
        return smtp_connection  # provide the fixture value

下面是`equipments`fixture更改为使用`addfinalizer`进行清理的情况：

    # content of test_yield3.py

    import contextlib
    import functools

    import pytest
    

    @contextlib.contextmanager
    def connect(port):
        ...  # create connection
        yield
        ...  # close connection
    

    @pytest.fixture
    def equipments(request):
        r = []
        for port in ("C1", "C3", "C28"):
            cm = connect(port)
            equip = cm.__enter__()
            request.addfinalizer(functools.partial(cm.__exit__, None, None, None))
            r.append(equip)
        return r

`yield`和`addfinalizer`方法的工作原理类似，都是在测试结束后调用它们的代码。当然，如果在终结函数注册之前发生了异常，那么它将不会被执行。

#### Fixtures可以内省请求的测试上下文

Fixture函数可以接收请求对象来内省“请求”测试函数、类或模块上下文。进一步扩展前面的`smtp_connection`fixture示例，让我们从使用我们的fixture的测试模块中读取一个可选的服务器URL:

    # content of conftest.py
    import pytest
    import smtplib
    

    @pytest.fixture(scope="module")
    def smtp_connection(request):
        server = getattr(request.module, "smtpserver", "smtp.gmail.com")
        smtp_connection = smtplib.SMTP(server, 587, timeout=5)
        yield smtp_connection
        print("finalizing {} ({})".format(smtp_connection, server))
        smtp_connection.close()

我们使用`request.module`属性从测试模块中有选择地获取`smtpserver`属性。 如果我们再次执行，什么都不会改变：

    $ pytest -s -q --tb=no
    FFfinalizing <smtplib.SMTP object at 0xdeadbeef> (smtp.gmail.com)

    ========================= short test summary info ==========================
    FAILED test_module.py::test_ehlo - assert 0
    FAILED test_module.py::test_noop - assert 0
    2 failed in 0.12s

让我们快速创建另一个测试模块，它实际在其模块命名空间中设置服务器URL:

    # content of test_anothersmtp.py

    smtpserver = "mail.python.org"  # 将由smtp fixture读取
    

    def test_showhelo(smtp_connection):
        assert 0, smtp_connection.helo()

运行它:

    $ pytest -qq --tb=short test_anothersmtp.py
    F                                                                    [100%]
    ================================= FAILURES =================================
    ______________________________ test_showhelo _______________________________
    test_anothersmtp.py:6: in test_showhelo
        assert 0, smtp_connection.helo()
    E   AssertionError: (250, b'mail.python.org')
    E   assert 0
    ------------------------- Captured stdout teardown -------------------------
    finalizing <smtplib.SMTP object at 0xdeadbeef> (mail.python.org)
    ========================= short test summary info ==========================
    FAILED test_anothersmtp.py::test_showhelo - AssertionError: (250, b'mail....

瞧！`smtp_connection` fixture函数从模块命名空间获取我们的邮件服务器名称。

#### fixtures工厂

"fixture工厂"模式可以在单个测试中多次需要fixture结果的情况下提供帮助。fixture没有直接返回数据，而是返回一个生成数据的函数。然后可以在测试中多次调用这个函数。

工厂可以根据需要设置参数：

    @pytest.fixture
    def make_customer_record():
        def _make_customer_record(name):
            return {"name": name, "orders": []}

        return _make_customer_record
    

    def test_customer_records(make_customer_record):
        customer_1 = make_customer_record("Lisa")
        customer_2 = make_customer_record("Mike")
        customer_3 = make_customer_record("Meredith")

如果工厂创建的数据需要管理，那么fixture可以处理这些数据：

    @pytest.fixture
    def make_customer_record():

        created_records = []

        def _make_customer_record(name):
            record = models.Customer(name=name, orders=[])
            created_records.append(record)
            return record

        yield _make_customer_record

        for record in created_records:
            record.destroy()
    

    def test_customer_records(make_customer_record):
        customer_1 = make_customer_record("Lisa")
        customer_2 = make_customer_record("Mike")
        customer_3 = make_customer_record("Meredith")

#### fixtures参数化

Fixture函数可以参数化，在这种情况下，它们将被调用多次，每次执行一组依赖测试，即依赖于这个fixture的测试。 测试函数通常不需要知道它们的重新运行。 fixtures参数化有助于为组件编写详尽的功能测试，这些组件本身可以通过多种方式进行配置。

扩展前面的示例，我们可以标记fixture来创建两个`smtp_connection`fixture实例，这将导致使用该fixture的所有测试运行两次。fixture函数通过特殊的request对象访问每个参数:

    # content of conftest.py
    import pytest
    import smtplib
    

    @pytest.fixture(scope="module", params=["smtp.gmail.com", "mail.python.org"])
    def smtp_connection(request):
        smtp_connection = smtplib.SMTP(request.param, 587, timeout=5)
        yield smtp_connection
        print("finalizing {}".format(smtp_connection))
        smtp_connection.close()

主要的更改是使用 @pytest.fixture声明`参数`，将执行fixture函数列表的每个值，并且可以通过`request.param`访问一个值。不需要更改测试函数代码。因此，让我们再进行一次运行：

    $ pytest -q test_module.py
    FFFF                                                                 [100%]
    ================================= FAILURES =================================
    ________________________ test_ehlo[smtp.gmail.com] _________________________

    smtp_connection = <smtplib.SMTP object at 0xdeadbeef>

        def test_ehlo(smtp_connection):
            response, msg = smtp_connection.ehlo()
            assert response == 250
            assert b"smtp.gmail.com" in msg
    >       assert 0  # for demo purposes
    E       assert 0

    test_module.py:7: AssertionError
    ________________________ test_noop[smtp.gmail.com] _________________________

    smtp_connection = <smtplib.SMTP object at 0xdeadbeef>

        def test_noop(smtp_connection):
            response, msg = smtp_connection.noop()
            assert response == 250
    >       assert 0  # for demo purposes
    E       assert 0

    test_module.py:13: AssertionError
    ________________________ test_ehlo[mail.python.org] ________________________

    smtp_connection = <smtplib.SMTP object at 0xdeadbeef>

        def test_ehlo(smtp_connection):
            response, msg = smtp_connection.ehlo()
            assert response == 250
    >       assert b"smtp.gmail.com" in msg
    E       AssertionError: assert b'smtp.gmail.com' in b'mail.python.org\nPIPELINING\nSIZE 51200000\nETRN\nSTARTTLS\nAUTH DIGEST-MD5 NTLM CRAM-MD5\nENHANCEDSTATUSCODES\n8BITMIME\nDSN\nSMTPUTF8\nCHUNKING'

    test_module.py:6: AssertionError
    -------------------------- Captured stdout setup ---------------------------
    finalizing <smtplib.SMTP object at 0xdeadbeef>
    ________________________ test_noop[mail.python.org] ________________________

    smtp_connection = <smtplib.SMTP object at 0xdeadbeef>

        def test_noop(smtp_connection):
            response, msg = smtp_connection.noop()
            assert response == 250
    >       assert 0  # for demo purposes
    E       assert 0

    test_module.py:13: AssertionError
    ------------------------- Captured stdout teardown -------------------------
    finalizing <smtplib.SMTP object at 0xdeadbeef>
    ========================= short test summary info ==========================
    FAILED test_module.py::test_ehlo[smtp.gmail.com] - assert 0
    FAILED test_module.py::test_noop[smtp.gmail.com] - assert 0
    FAILED test_module.py::test_ehlo[mail.python.org] - AssertionError: asser...
    FAILED test_module.py::test_noop[mail.python.org] - assert 0
    4 failed in 0.12s

我们可以看到，我们的两个测试函数分别针对不同的`smtp_connection`实例运行了两次。还要注意，对于`mail.python.org`连接，第二个测试在`test_ehlo`中失败，因为预期的服务器字符串与达到的字符串不同。

pytest将构建一个字符串，该字符串是参数化fixture中的每个fixture值的测试ID，例如上面例子中的`test_ehlo[smtl.gmail.com]`和`test_ehlo[mail.python.org]`。这些id可以与`-k`一起使用，以选择要运行的特定情况，并且它们还将在失败时识别特定情况。使用`--collect-only`运行pytest将显示生成的ID。

数字、字符串、布尔值和None将在测试ID中使用它们通常的字符串表示形式。对于其他对象，pytest将基于参数名创建一个字符串。可以使用`ids`关键字参数自定义测试ID中用于某个fixture值的字符串:

    # content of test_ids.py
    import pytest
    

    @pytest.fixture(params=[0, 1], ids=["spam", "ham"])
    def a(request):
        return request.param
    

    def test_a(a):
        pass
    

    def idfn(fixture_value):
        if fixture_value == 0:
            return "eggs"
        else:
            return None
    

    @pytest.fixture(params=[0, 1], ids=idfn)
    def b(request):
        return request.param
    

    def test_b(b):
        pass

上面展示了如何将`ids`作为要使用的字符串列表，或者使用fixture值调用的函数，然后返回要使用的字符串。在后一种情况下，如果函数返回`None`，则使用pytest自动生成的ID。

运行上述测试会导致使用以下测试ID：

    $ pytest --collect-only
    =========================== test session starts ============================
    platform linux -- Python 3.x.y, pytest-5.x.y, py-1.x.y, pluggy-0.x.y
    cachedir: $PYTHON_PREFIX/.pytest_cache
    rootdir: $REGENDOC_TMPDIR
    collected 10 items
    <Module test_anothersmtp.py>
      <Function test_showhelo[smtp.gmail.com]>
      <Function test_showhelo[mail.python.org]>
    <Module test_ids.py>
      <Function test_a[spam]>
      <Function test_a[ham]>
      <Function test_b[eggs]>
      <Function test_b[1]>
    <Module test_module.py>
      <Function test_ehlo[smtp.gmail.com]>
      <Function test_noop[smtp.gmail.com]>
      <Function test_ehlo[mail.python.org]>
      <Function test_noop[mail.python.org]>

    ========================== no tests ran in 0.12s ===========================

#### 使用带有参数化fixtures的标记

[pytest.param()](https://docs.pytest.org/en/latest/reference.html#pytest.param) 可用于在参数化fixtures的值集中应用标记，其方式与使用 [@pytest.mark.parametrize](https://docs.pytest.org/en/latest/parametrize.html#pytest-mark-parametrize) 相同。

示例：

    # content of test_fixture_marks.py
    import pytest
    

    @pytest.fixture(params=[0, 1, pytest.param(2, marks=pytest.mark.skip)])
    def data_set(request):
        return request.param
    

    def test_data(data_set):
        pass

运行此测试将跳过对值`2`的`data_set`的调用：

    $ pytest test_fixture_marks.py -v
    =========================== test session starts ============================
    platform linux -- Python 3.x.y, pytest-5.x.y, py-1.x.y, pluggy-0.x.y -- $PYTHON_PREFIX/bin/python
    cachedir: $PYTHON_PREFIX/.pytest_cache
    rootdir: $REGENDOC_TMPDIR
    collecting ... collected 3 items

    test_fixture_marks.py::test_data[0] PASSED                           [ 33%]
    test_fixture_marks.py::test_data[1] PASSED                           [ 66%]
    test_fixture_marks.py::test_data[2] SKIPPED                          [100%]

    ======================= 2 passed, 1 skipped in 0.12s =======================

#### 模块化：使用fixture函数中的fixtures

除了在测试函数中使用fixtures外，fixture函数本身也可以使用其他fixtures。这有助于fixtures的模块化设计，并允许跨许多项目重用特定于框架的fixtures。作为一个简单的例子，我们可以扩展前面的例子，并实例化一个对象`app`程序，我们将已经定义好的`smtp_connection`资源插入其中:

    # content of test_appsetup.py
    
    import pytest

    class App:
        def __init__(self, smtp_connection):
            self.smtp_connection = smtp_connection
    

    @pytest.fixture(scope="module")
    def app(smtp_connection):
        return App(smtp_connection)
    

    def test_smtp_connection_exists(app):
        assert app.smtp_connection

这里我们声明一个`app`fixture，它接收前面定义的`smtp_connection`fixture并使用它实例化一个`App`对象。让我们运行它：

    $ pytest -v test_appsetup.py
    =========================== test session starts ============================
    platform linux -- Python 3.x.y, pytest-5.x.y, py-1.x.y, pluggy-0.x.y -- $PYTHON_PREFIX/bin/python
    cachedir: $PYTHON_PREFIX/.pytest_cache
    rootdir: $REGENDOC_TMPDIR
    collecting ... collected 2 items

    test_appsetup.py::test_smtp_connection_exists[smtp.gmail.com] PASSED [ 50%]
    test_appsetup.py::test_smtp_connection_exists[mail.python.org] PASSED [100%]

    ============================ 2 passed in 0.12s =============================

由于`smtp_connection`的参数化，该测试将在两个不同的`App`实例和各自的smtp服务器上运行两次。`app`fixture不需要知道`smtp_connection`参数化，因为pytest将完全分析fixture依赖关系图。

注意，`app`fixture有一个`模块`作用域，并使用一个模块作用域的`smtp_connection` fixture。如果将`smtp_connection`缓存在`会话`作用域中，则该示例仍然可以工作：fixtures可以使用"更广泛"作用域的fixtures，反之则不行:一个会话作用域内的fixture使用一个模块作用域内的fixture是没有意义的方式。

#### 按照fixture实例自动将测试分组

pytest在测试运行期间最大程度地减少了活动fixtures的数量。然后使用它的所有测试将首先使用一个实例执行，然后在创建下一个fixture实例之前调用终结器。除此之外，这还简化了对创建和使用全局状态的应用程序的测试。

下面的例子使用了两个参数化的fixtures，其中一个基于每个模块，所有函数都执行`打印`调用来显示设置/拆卸流程:

    # content of test_module.py
    import pytest
    

    @pytest.fixture(scope="module", params=["mod1", "mod2"])
    def modarg(request):
        param = request.param
        print("  SETUP modarg", param)
        yield param
        print("  TEARDOWN modarg", param)
    

    @pytest.fixture(scope="function", params=[1, 2])
    def otherarg(request):
        param = request.param
        print("  SETUP otherarg", param)
        yield param
        print("  TEARDOWN otherarg", param)
    

    def test_0(otherarg):
        print("  RUN test0 with otherarg", otherarg)
    

    def test_1(modarg):
        print("  RUN test1 with modarg", modarg)
    

    def test_2(otherarg, modarg):
        print("  RUN test2 with otherarg {} and modarg {}".format(otherarg, modarg))

让我们以详细模式运行测试，并查看打印输出:

    $ pytest -v -s test_module.py
    =========================== test session starts ============================
    platform linux -- Python 3.x.y, pytest-5.x.y, py-1.x.y, pluggy-0.x.y -- $PYTHON_PREFIX/bin/python
    cachedir: $PYTHON_PREFIX/.pytest_cache
    rootdir: $REGENDOC_TMPDIR
    collecting ... collected 8 items

    test_module.py::test_0[1]   SETUP otherarg 1
      RUN test0 with otherarg 1
    PASSED  TEARDOWN otherarg 1

    test_module.py::test_0[2]   SETUP otherarg 2
      RUN test0 with otherarg 2
    PASSED  TEARDOWN otherarg 2

    test_module.py::test_1[mod1]   SETUP modarg mod1
      RUN test1 with modarg mod1
    PASSED
    test_module.py::test_2[mod1-1]   SETUP otherarg 1
      RUN test2 with otherarg 1 and modarg mod1
    PASSED  TEARDOWN otherarg 1

    test_module.py::test_2[mod1-2]   SETUP otherarg 2
      RUN test2 with otherarg 2 and modarg mod1
    PASSED  TEARDOWN otherarg 2

    test_module.py::test_1[mod2]   TEARDOWN modarg mod1
      SETUP modarg mod2
      RUN test1 with modarg mod2
    PASSED
    test_module.py::test_2[mod2-1]   SETUP otherarg 1
      RUN test2 with otherarg 1 and modarg mod2
    PASSED  TEARDOWN otherarg 1

    test_module.py::test_2[mod2-2]   SETUP otherarg 2
      RUN test2 with otherarg 2 and modarg mod2
    PASSED  TEARDOWN otherarg 2
      TEARDOWN modarg mod2
    

    ============================ 8 passed in 0.12s =============================

您可以看到，参数化的模块作用域`modarg`资源导致了测试执行的顺序，从而导致了尽可能少的“活动”资源。在设置`mod2`资源之前，执行`mod1`参数化资源的终结器。

特别要注意的是，test_0是完全独立的，并且是最先完成的。然后使用mod1执行test_1，再用mod1执行test 2，再用mod2执行test 1，最后用mod2执行test 2。

`otherarg`参数化资源（具有函数作用域）是在使用它的每个测试之前设置的，并在使用它的每个测试后被拆除。

#### 使用类，模块或项目中的fixture

有时测试函数不需要直接访问fixture对象。例如，测试可能需要使用一个空目录作为当前工作目录，但不关心具体目录。下面介绍如何使用标准的 [tempfile](http://docs.python.org/library/tempfile.html) 和pytest fixture来实现它。我们将fixture的创建分离到conftest.py文件中:

    # content of conftest.py

    import os
    import shutil
    import tempfile

    import pytest
    

    @pytest.fixture
    def cleandir():
        old_cwd = os.getcwd()
        newpath = tempfile.mkdtemp()
        os.chdir(newpath)
        yield
        os.chdir(old_cwd)
        shutil.rmtree(newpath)

并通过`usefixtures`标记在测试模块中声明其使用：

    # content of test_setenv.py
    import os
    import pytest
    

    @pytest.mark.usefixtures("cleandir")
    class TestDirectoryInit:
        def test_cwd_starts_empty(self):
            assert os.listdir(os.getcwd()) == []
            with open("myfile", "w") as f:
                f.write("hello")

        def test_cwd_again_starts_empty(self):
            assert os.listdir(os.getcwd()) == []

由于使用了`usefixture`标记，所以在执行每个测试方法时都需要`cleandir` fixture，就像您为每个测试方法指定了一个"cleandir"函数参数一样。让我们运行它来验证我们的fixture是否被激活并且测试是否通过:

    $ pytest -q
    ..                                                                   [100%]
    2 passed in 0.12s

您可以像这样指定多个fixture:

    @pytest.mark.usefixtures("cleandir", "anotherfixture")
    def test():
        ...

您可以使用标记机制的一般特性在测试模块级别指定fixture的使用:

    pytestmark = pytest.mark.usefixtures("cleandir")

注意，指定的变量必须称为`pytestmark`，例如，`foomark`将不会激活fixture。

也可以将项目中所有测试所需的fixtures放入一个ini文件中:

    # content of pytest.ini
    [pytest]
    usefixtures = cleandir

><font size=5>警告：</font>  
注意，此标记在fixture函数中没有影响。例如，这将不会像预期的那样工作:
>
>&nbsp; &nbsp; @pytest.mark.usefixtures("my_other_fixture")  
&nbsp; &nbsp; @pytest.fixture  
&nbsp; &nbsp; def my_fixture_that_sadly_wont_use_my_other_fixture():  
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;...  
>
>目前，这将不会生成任何错误或警告，但这将由[#3664](https://github.com/pytest-dev/pytest/issues/3664)处理。

#### 自动使用fixtures(xUnit setup on steroids)

有时候，您可能希望在没有显式声明函数参数或[usefixture](https://docs.pytest.org/en/latest/fixture.html#usefixtures)修饰符的情况下自动调用fixture。作为一个实际的示例，假设我们有一个具有开始/回滚/提交架构的数据库设备，并且我们希望通过事务和回滚来自动围绕每种测试方法。下面是这个想法的一个虚拟的自包含的实现:

    # content of test_db_transact.py

    import pytest
    

    class DB:
        def __init__(self):
            self.intransaction = []

        def begin(self, name):
            self.intransaction.append(name)

        def rollback(self):
            self.intransaction.pop()
    

    @pytest.fixture(scope="module")
    def db():
        return DB()
    

    class TestClass:
        @pytest.fixture(autouse=True)
        def transact(self, request, db):
            db.begin(request.function.__name__)
            yield
            db.rollback()

        def test_method1(self, db):
            assert db.intransaction == ["test_method1"]

        def test_method2(self, db):
            assert db.intransaction == ["test_method2"]

类级别的事务fixture标记为autouse=true，这意味着类中的所有测试方法都将使用这个fixture，而不需要在测试函数签名中声明它，也不需要使用类级别的usefixture修饰符。

如果我们运行它，我们会得到两个通过的测试:

    $ pytest -q
    ..                                                                   [100%]
    2 passed in 0.12s

这是autouse fixtures在其他作用域中的工作方式：

* autouse fixture遵循`scope =`关键字参数：如果一个autouse fixture具有`scope='session'`，那么它将只运行一次，不管它是在哪里定义的。`scope='class'`意味着它将在每个类中运行一次，等等。
* 如果在测试模块中定义了autouse fixture，那么它的所有测试函数都会自动使用它。
* 如果autouse fixture是在conftest.py文件中定义的，那么其目录下的所有测试模块中的所有测试都将调用该fixture。
* 最后，请小心使用:如果您在插件中定义了一个autouse fixture，那么它将在安装插件的所有项目的所有测试中被调用。如果一个fixture仅在某些设置(例如在ini文件中)存在的情况下工作，那么这将非常有用。这样的全局fixture应始终快速确定它是否应该做任何工作，并避免其他昂贵的导入或计算。

请注意，上面的事务fixture很可能是您希望在项目中使用的fixture，而不需要使其处于活动状态。要做到这一点的标准方法是将事务定义放入conftest.py文件中，而不使用autouse:

    # content of conftest.py
    @pytest.fixture
    def transact(request, db):
        db.begin()
        yield
        db.rollback()

然后，例如，让一个TestClass通过声明需要来使用它:

    @pytest.mark.usefixtures("transact")
    class TestClass:
        def test_method1(self):
            ...

这个TestClass中的所有测试方法将使用事务fixture，而模块中的其他测试类或函数将不使用它，除非它们也添加了一个`transact`引用。

#### 覆盖各个级别的fixture

在相对较大的测试套件中，您很可能需要用本地定义的fixture覆盖全局fixture或根fixture，以保持测试代码的可读性和可维护性。

##### 覆盖文件夹(conftest)级别上的fixture

给定测试文件结构为:

    tests/
        __init__.py
    
        conftest.py
            # content of tests/conftest.py
            import pytest
    
            @pytest.fixture
            def username():
                return 'username'
    
        test_something.py
            # content of tests/test_something.py
            def test_username(username):
                assert username == 'username'
    
        subfolder/
            __init__.py
    
            conftest.py
                # content of tests/subfolder/conftest.py
                import pytest
    
                @pytest.fixture
                def username(username):
                    return 'overridden-' + username
    
            test_something.py
                # content of tests/subfolder/test_something.py
                def test_username(username):
                    assert username == 'overridden-username'

如您所见，对于某些测试文件夹级别，具有相同名称的fixture可以被覆盖。请注意，可以容易地从覆盖的fixture访问基础或超级fixture-在以上示例中使用。

##### 在测试模块级别覆盖夹具

给定测试文件结构为：

    tests/
        __init__.py
    
        conftest.py
            # content of tests/conftest.py
            import pytest
    
            @pytest.fixture
            def username():
                return 'username'
    
        test_something.py
            # content of tests/test_something.py
            import pytest
    
            @pytest.fixture
            def username(username):
                return 'overridden-' + username
    
            def test_username(username):
                assert username == 'overridden-username'
    
        test_something_else.py
            # content of tests/test_something_else.py
            import pytest
    
            @pytest.fixture
            def username(username):
                return 'overridden-else-' + username
    
            def test_username(username):
                assert username == 'overridden-else-username'

在上面的示例中，可以为某些测试模块覆盖具有相同名称的fixture。

##### 通过直接测试参数化覆盖fixture

给定测试文件结构为：

    tests/
        __init__.py
    
        conftest.py
            # content of tests/conftest.py
            import pytest
    
            @pytest.fixture
            def username():
                return 'username'
    
            @pytest.fixture
            def other_username(username):
                return 'other-' + username
    
        test_something.py
            # content of tests/test_something.py
            import pytest
    
            @pytest.mark.parametrize('username', ['directly-overridden-username'])
            def test_username(username):
                assert username == 'directly-overridden-username'
    
            @pytest.mark.parametrize('username', ['directly-overridden-username-other'])
            def test_username_other(other_username):
                assert other_username == 'other-directly-overridden-username-other'

在上面的例子中，测试参数值覆盖了一个fixture值。请注意，即使测试没有直接使用fixture(在函数原型中没有提到它)，也可以通过这种方式覆盖fixture的值。

##### 用非参数化的参数覆盖参数化的fixture，反之亦然

给定测试文件结构为：

    tests/
        __init__.py
    
        conftest.py
            # content of tests/conftest.py
            import pytest
    
            @pytest.fixture(params=['one', 'two', 'three'])
            def parametrized_username(request):
                return request.param
    
            @pytest.fixture
            def non_parametrized_username(request):
                return 'username'
    
        test_something.py
            # content of tests/test_something.py
            import pytest
    
            @pytest.fixture
            def parametrized_username():
                return 'overridden-username'
    
            @pytest.fixture(params=['one', 'two', 'three'])
            def non_parametrized_username(request):
                return request.param
    
            def test_username(parametrized_username):
                assert parametrized_username == 'overridden-username'
    
            def test_parametrized_username(non_parametrized_username):
                assert non_parametrized_username in ['one', 'two', 'three']
    
        test_something_else.py
            # content of tests/test_something_else.py
            def test_username(parametrized_username):
                assert parametrized_username in ['one', 'two', 'three']
    
            def test_username(non_parametrized_username):
                assert non_parametrized_username == 'username'

在上面的例子中，一个参数化的fixture被一个非参数化的版本覆盖，一个非参数化的fixture被某个测试模块的参数化版本覆盖。显然，这同样适用于测试文件夹级别。

