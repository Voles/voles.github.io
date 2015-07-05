---
layout: post
title: "Getting started with Python"
date: 2013-04-20 15:59
comments: true
categories: [Python, introduction, tutorial]
---

It's been a while now since I've written my first line of Python code. With this blogpost I'd like to share some knowledge, to make it easier for others to get started with Python. I assume you have some basic experience with the command line, and know what unittests are for.

Note: the commands below are written for Mac OSX

## Different versions of Python
There are two main versions of Python which are both still frequently used. The most recent version is Python 3, and there is also the older 2.7 version.

> Python 2.x is the status quo, Python 3.x is the present and future of the language

> <cite>[Python Wiki](http://wiki.python.org/moin/Python2orPython3 'Python2orPython3')</cite>

On the Python Wiki you can find more information about [which Python version to use](http://wiki.python.org/moin/Python2orPython3, 'Which Python version to use').

## Environment setup
It is common to setup a new environment when you start with a new Python project. The reason for this is that different projects will have different dependencies on other libraries.

You can install all of the dependencies globally, although thats not recommended. Once you switch to an other machine, or if you work in team, you have to make sure all the right version of each external library is installed.

Let's get started. First of all we install the right tools to set up an environment.

{% codeblock lang:bash %}
$ pip install virtualenv
{% endcodeblock %}

Next we create a new environment named 'my-environment', using the command `virtualenv`.

{% codeblock lang:bash %}
$ mkdir ~/Documents/environments/
$ cd ~/Documents/environments/
$ virtualenv my-environment --no-site-packages
{% endcodeblock %}

Now we can create a link to it, so we don't have to type the full path everytime we want to use the environment.

{% codeblock lang:bash %}
$ ln -s ~/Documents/environments/my-environment/bin/python /usr/bin/my-environment
{% endcodeblock %}

When you execute `$ my-environment`, you can immediately start writing code. Let's print something to the Terminal with `print "Hello, World!"`. When you write `2 + 3`, you will get `5` as a result.

That's it, you just evaluated your first two expressions in Python. Now we have our own Python environment where we can install and update all of the dependencies.

Writing your code directly in the Terminal is of course not recommended when you want to write serious programs.
Let's make a project for this environment.

## Project setup
Go to the project folder and create a file named `math.py` with the following content.

{% codeblock lang:python %}
# -*- coding: utf-8 -*-
'''
[2013] Niels Dequeker
 All Rights Reserved.
'''

class Math(object):

        def sum(self, a, b):
                return a + b

        def times(self, a, b):
                return a * b

        def divide(self, a, b):
                return a / b
{% endcodeblock %}

This is how we write a basic class in Python. It has three methods, `sum`, `times` and `divide`.

Now we can write some unittests to validate our code. Create a file named `tests.py` with the following content.

{% codeblock lang:python %}
# -*- coding: utf-8 -*-
'''
[2012] SocialExpress
 All Rights Reserved.
'''
import unittest
from math import Math

class Test(unittest.TestCase):

    def test_sum(self):
        math = Math()
        self.assertTrue(math.sum(2, 3) == 5, 'Incorrect sum')
   
    def test_times(self):
        math = Math()
        self.assertTrue(math.times(2, 2) == 4, 'Incorrect times')

    def test_divide(self):
        math = Math()
        self.assertTrue(math.divide(12, 6) == 2, 'Incorrect division')

if __name__ == "__main__":
    unittest.main()
{% endcodeblock %}

Let's go through the code step by step.

First of all we import our dependencies. `Math` is our own class that we've created before.

{% codeblock lang:python %}
import unittest
from math import Math
{% endcodeblock %}

Next is the class definition for the test. It extends from `unittest.TestCase`.

{% codeblock lang:python %}
class Test(unittest.TestCase):
{% endcodeblock %}

Now what follows are the methods. Each one is testing one functionality of our `Math` class. We check the return values with `assertTrue` and get an exception when these aren't what we expected.

{% codeblock lang:python %}
def test_sum(self):
        math = Math()
        self.assertTrue(math.sum(2, 3) == 5, 'Incorrect sum')        {% endcodeblock %}

Finally, we define that if the `tests.py` file is executed directly, it has to execute our tests.

{% codeblock lang:python %}
if __name__ == "__main__":
    unittest.main()
{% endcodeblock %}

That's it. We can run our code in the Terminal with `$ my-environment tests.py`. You should see `Ran 3 tests`, which mean your code works as expected.

## Further reference
- [Getting Started with Python on Codeacademy](http://www.codecademy.com/courses/getting-started-with-python, 'Getting Started with Python on Codeacademy')
- [The Python tutorial](http://docs.python.org/2/tutorial/, 'The Python tutorial')
- [Python homepage](www.python.com 'Python homepage')