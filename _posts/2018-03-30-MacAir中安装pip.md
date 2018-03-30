
安装pip要是easy_install命令，如果使用brew install命令会出错

## 正确方式

```
➜  nova git:(ksc_folsom_vpc_ebs_tmp_review) sudo easy_install pip
Password:
Searching for pip
Reading https://pypi.python.org/simple/pip/
Best match: pip 9.0.3
Downloading https://pypi.python.org/packages/c4/44/e6b8056b6c8f2bfd1445cc9990f478930d8e3459e9dbf5b8e2d2922d64d3/pip-9.0.3.tar.gz#md5=b15b33f9aad61f88d0f8c866d16c55d8
Processing pip-9.0.3.tar.gz
Writing /tmp/easy_install-FQ2AJM/pip-9.0.3/setup.cfg
Running pip-9.0.3/setup.py -q bdist_egg --dist-dir /tmp/easy_install-FQ2AJM/pip-9.0.3/egg-dist-tmp-jojmR0
/System/Library/Frameworks/Python.framework/Versions/2.7/lib/python2.7/distutils/dist.py:267: UserWarning: Unknown distribution option: 'python_requires'
  warnings.warn(msg)
warning: no previously-included files found matching '.coveragerc'
warning: no previously-included files found matching '.mailmap'
warning: no previously-included files found matching '.travis.yml'
warning: no previously-included files found matching '.landscape.yml'
warning: no previously-included files found matching 'pip/_vendor/Makefile'
warning: no previously-included files found matching 'tox.ini'
warning: no previously-included files found matching 'dev-requirements.txt'
warning: no previously-included files found matching 'appveyor.yml'
no previously-included directories found matching '.github'
no previously-included directories found matching '.travis'
no previously-included directories found matching 'docs/_build'
no previously-included directories found matching 'contrib'
no previously-included directories found matching 'tasks'
no previously-included directories found matching 'tests'
creating /Library/Python/2.7/site-packages/pip-9.0.3-py2.7.egg
Extracting pip-9.0.3-py2.7.egg to /Library/Python/2.7/site-packages
Adding pip 9.0.3 to easy-install.pth file
Installing pip script to /usr/local/bin
Installing pip2.7 script to /usr/local/bin
Installing pip2 script to /usr/local/bin

Installed /Library/Python/2.7/site-packages/pip-9.0.3-py2.7.egg
Processing dependencies for pip
Finished processing dependencies for pip
```

执行命令```sudo easy_install pip```,输入密码后，自动安装完成，必须sudo否则会提示权限错误。

```
➜  nova git:(ksc_folsom_vpc_ebs_tmp_review) easy_install pip
error: can't create or remove files in install directory

The following error occurred while trying to add or remove files in the
installation directory:

    [Errno 13] Permission denied: '/Library/Python/2.7/site-packages/test-easy-install-33495.pth'
```

## 错误方式

```
➜  nova git:(ksc_folsom_vpc_ebs_tmp_review) brew install pip
Error: No available formula with the name "pip"
Homebrew provides pip via: `brew install python`. However you will then
have two Pythons installed on your Mac, so alternatively you can install
pip via the instructions at:
  https://pip.readthedocs.io/en/stable/installing/
```

如错误信息，在这种方式中，pip是和python一起的，这样mac中就会安装两套python，所以这样会对环境造成影响。



