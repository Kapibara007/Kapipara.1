from random import randint
from PyQt5.QtCore import Qt
from PyQt5.QtWidgets import QApplication, QWidget, QLabel, QRadioButton, QMessageBox, QVBoxLayout, QPushButton
app = QApplication([])
window = QWidget()
window.setWindowTitle('lacki')
window.resize(200, 100)

welcome = QLabel('Добро пожаловать в гениратор паролей!')
Start = QPushButton('Сгенерировать')
vline = QVBoxLayout()
vline.addWidget(welcome, alignment=Qt.AlignCenter)
vline.addWidget(Start, stretch=2, alignment=Qt.AlignCenter)
window.setLayout(vline)
def create_pas():
    alphabet = 'abcdefghijklmnopqrstuvwxyz'
    numbers = '0123456789'
    n = 8
    password = ''
    for i in range(8):
        res = randint(1, 2)
        if res == 1:
            alpha = randint(0, 25)
            password += alphabet[alpha]
        else:
            num = randint(0, 9)
            password += numbers[num]
    return password

def button():
    vin = QMessageBox()
    vin.setText(create_pas())
    vin.exec_()

Start.clicked.connect(button)
window.show()
app.exec_()
