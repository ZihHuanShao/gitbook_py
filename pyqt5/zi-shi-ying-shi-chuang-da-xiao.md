# 自適應視窗大小



```python
import sys
import sys
from PyQt5.QtCore import *
from PyQt5.QtGui import *
from PyQt5.QtWidgets import *


class Example(QWidget):
    def __init__(self):
        super(Example, self).__init__()
        self.initUI()

    def initUI(self):
        cal = QCalendarWidget(self)
        cal.setGridVisible(True)
        # cal.move(0, 0)

        # self.setGeometry(0, 0, 500, 500)
        self.resize(cal.sizeHint())
        
        self.setWindowTitle('Calendar')
        self.show()

def main():
    app = QApplication(sys.argv)
    ex = Example()

    sys.exit(app.exec_())


if __name__ == '__main__':
    main()
```

試將18與19行分別註解執行測試

##  Ref.

{% embed url="https://blog.csdn.net/Dontla/article/details/105507591" caption="button為自適應大小的widget" %}





