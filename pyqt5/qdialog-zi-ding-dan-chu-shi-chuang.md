# QDialog 自訂彈出視窗



```python
import sys
from PyQt5.QtCore import *
from PyQt5.QtGui import *
from PyQt5.QtWidgets import *

class window(QWidget):
    def __init__(self):
        super().__init__()
        self.initUI()

    def initUI(self):
        self.btn = QPushButton("Hello World!", self)
        self.btn.setText("Hello World!")
        self.btn.move(100,50)
        self.btn.clicked.connect(self.showdialog) # 顯示彈出視窗
        self.setWindowTitle("PyQt Dialog demo")

    def showdialog(self):
        self.dlg = QDialog()
        
        self.b1 = QPushButton("ok",self.dlg)
        self.b1.move(50,50)
        self.b1.clicked.connect(self.close)
        
        self.dlg.setWindowTitle("Dialog")
        self.dlg.setWindowModality(Qt.ApplicationModal)
        self.dlg.exec_()

    def close(self):
        self.dlg.close() # 關閉彈出視窗

if __name__ == '__main__':
    app = QApplication(sys.argv)
    w = window()
    w.show()

    sys.exit(app.exec_())
```

##  Ref.

{% embed url="https://www.tutorialspoint.com/pyqt5/pyqt5\_qdialog\_class.htm" %}



