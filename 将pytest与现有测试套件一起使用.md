Pytest可以与大多数现有的测试套件一起使用，但是它的行为与其他测试运行程序不同，比如 [nose](https://docs.pytest.org/en/latest/nose.html#noseintegration) 或Python的默认unittest框架。

在使用本节之前，您需要安装pytest。

#### 使用pytest运行现有的测试套件
假设您想为某个地方的现有存储库做出贡献。在使用一些版本控制和(可选的)设置代码到你的开发空间后，你会想要运行:

    cd <repository>
    pip install -e .  # Environment dependent alternatives include
                      # 'python setup.py develop' and 'conda develop'
                 
在您的项目根目录中。这将在站点程序包中设置一个到代码的符号链接，使您可以在针对代码运行测试时像编辑代码一样对其进行编辑。

在开发模式下设置项目，可以避免每次运行测试时都要重新安装，而且比在sys上瞎折腾要简单得多。将测试指向本地代码的路径。

也可以考虑使用 [tox](https://docs.pytest.org/en/latest/goodpractices.html#use-tox)。

