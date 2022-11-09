# PyQt5-interface


from PyQt6.QtWidgets import (
    QApplication, QVBoxLayout, QWidget, QLabel, QPushButton
)
from PyQt6.QtCore import Qt
import sys
from PyQt6.QtGui import QIcon




class Window(QWidget):
    def __init__(self):
        super().__init__()
        self.resize(350, 275)
        self.setWindowTitle("CodersLegacy")

        layout = QVBoxLayout()
        self.setLayout(layout)

        self.label = QLabel("Фу")
        self.label.setAlignment(Qt.AlignmentFlag.AlignCenter)
        self.label.adjustSize()
        layout.addWidget(self.label)

        button = QPushButton("обновить текст")
        button.clicked.connect(self.update)
        layout.addWidget(button)

        button = QPushButton("Распечатать \n тест")
        button.clicked.connect(self.get)
        layout.addWidget(button)

        button = QPushButton("Выйти из \n программы", self)
        button.clicked.connect(self.close)
        button.resize(120, 60)
        button.move(120, 15)
        button.setIcon(QIcon('482-4821482_art-courtesy-of-nima-sotoudeh-elon-musk-smoking.png'))

        button = QPushButton("О программе", self)
        button.clicked.connect(self.close)
        button.resize(120, 100)
        button.move(250, 15)
        button.setIcon(QIcon('482-4821482_art-courtesy-of-nima-sotoudeh-elon-musk-smoking.png'))

    def update(self):
        self.label.setText("Я у мамы программист")

    def get(self):
        print(self.label.text())


app = QApplication(sys.argv)
window = Window()
window.show()
sys.exit(app.exec())
