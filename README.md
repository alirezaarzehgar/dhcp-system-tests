# dhcp system tests
This is a collection of all dhcp tests for DHCP Test Driven Development
You can add this tests on your dhcp projects and run them over network for system testing

## usage

When you want to add a module to this system you should create a file (or project depend on your needs) on `modules` folder.

Then you should create a endpoint that contain a class inherit Runanle interface.

For example we create `demo.py` on modules and put following codes :

```python
from python_test_system.TestSystem.Runable import Runable


class Demo(Runable):
    def run():
        print("hello")
```

Then you should add this class to main.py

```python
+ from modules.demo import Demo
from python_test_system import TestSystem


if __name__ == '__main__':
    testSystem = TestSystem.TestSystem()

    testSystem.iterate([
+       Demo
    ])
```