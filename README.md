
Application with Internal Packages
===

In larger applications, you may have one or more internal packages that are either tied together with a main runner script or that provide specific functionality to a larger library you are packaging.

```
python-project-template
├── LICENSE
├── Makefile
├── README.md
├── bin
├── data
├── docs
│   ├── Makefile
│   ├── conf.py
│   ├── index.rst
│   └── make.bat
├── requirements.txt
├── setup.py
├── src
│   ├── __init__.py
│   ├── hello
│   │   ├── __init__.py
│   │   ├── hello.py
│   │   └── helpers.py
│   ├── runner.py
│   └── world
│       ├── __init__.py
│       ├── helpers.py
│       └── world.py
└── tests
    ├── __init__.py
    ├── context.py
    ├── test_advanced.py
    └── test_basic.py
```

* **bin/**  : This directory holds any executable files. The most important point to remember is that your executable shouldn’t have a lot of code, just an import and a call to a main function in your runner script. If you are using pure Python or don’t have any executable files, you can leave out this directory.
* **data/** : Having this directory is helpful for testing. It’s a central location for any files that your application will ingest or produce. Depending on how you deploy your application, you can keep “production-level” inputs and outputs pointed to this directory, or only use it for internal testing.
* **docs/** : With a more advanced application, you’ll want to maintain good documentation of all its parts. I like to put any documentation for internal modules here, which is why you see separate documents for the hello and world packages. If you use docstrings in your internal modules (and you should!), your whole-module documentation should at the very least give a holistic view of the purpose and function of the module.
* **src/**  : The directory contains source code, but now there are subdirectories. As you add more complexity, you’ll want to use a “divide and conquer” tactic and split out parts of your application logic into more manageable chunks. Remember that the directory name refers to the overall package name, and so the subdirectory names (hello/ and world/) should reflect their package names.
* **test/** : Here, you can put all your tests—unit tests, execution tests, integration tests, and so on. Feel free to structure this directory in the most convenient way for your testing strategies, import strategies, and more.
* **LICENSE** : The license for this project
* **Makefile** : A makefile to compile this project
* **requirements.txt** : A list of required python packages
* **setup.py** : A setup file for python projects
* **README.md** : A readme file


How to install this python package
===

How to execute this project in Unix/Linux Environment
===
```batch
python3 src/runner.py
```


Reference
===
1. [Unresolved references inspection](https://intellij-support.jetbrains.com/hc/en-us/community/posts/115000646984--Solved-Warnings-import-local-package-Unresolved-references-inspection)