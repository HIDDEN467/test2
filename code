from PyQt5.QtCore import Qt
from PyQt5.QtWidgets import *
from random import *


app = QApplication([])
main_window = QWidget()
main_window.setWindowTitle('Memory Card')
main_window.resize(500, 500)
RadioGroupBox = QGroupBox('Варианты ответов:')
otvet1 = QRadioButton('Энцы')
otvet2 = QRadioButton('Смурфы')
otvet3 = QRadioButton('Чулымцы')
otvet4 = QRadioButton('Алеуты')
knopki = [otvet1, otvet2, otvet3, otvet4]
z = 1
b = 0
class Question():
    def __init__(self, question, pravilniy, neprav1, neprav2, neprav3):
        self.question = question
        self.pravilniy = pravilniy
        self.neprav1 = neprav1
        self.neprav2 = neprav2
        self.neprav3 = neprav3

q = Question('Какой национальности не существует?', 'Смурфы', 'Энцы', 'Чулымцы', 'Алеуты')
q2 = Question('Госудаственный язы Бразилии?', 'Португальский', 'Английский', 'Испанский', 'Бразильский')
q3 = Question('Какого моря не существует?', 'Зелёное', 'Белое', 'Красное', 'Чёрное')      
q4 = Question('Какое животное является рогатым скотом?', 'Корова', 'Свинья', 'Курица', 'Лошадь')
q5 = Question('Самое популярное зерновое растение?', 'Пшеница', 'Ячмень', 'Гречневая', 'Рис')

voprosi = [q, q2, q3, q4, q5]
main_window.cur_question = -1
def show_result():
    RadioGroupBox.hide()
    Group.show()
    button.setText('Следующий вопрос')
def show_question():
    Group.hide()
    RadioGroupBox.show()
    button.setText('Ответить')
    RadioGroup.setExclusive(False)
    otvet1.setChecked(False)
    otvet2.setChecked(False)
    otvet3.setChecked(False)
    otvet4.setChecked(False)
    RadioGroup.setExclusive(True)
def start_test():
    if button.text() == 'Ответить':
        show_result()
    elif button.text() == 'Следующий вопрос':
        next_quetion(z)
        show_question()
def ask(q):
    shuffle(knopki)
    knopki[0].setText(q.pravilniy)
    knopki[1].setText(q.neprav1)
    knopki[2].setText(q.neprav2)
    knopki[3].setText(q.neprav3)
    question434.setText(q.question)
    pravilno.setText(q.pravilniy)
    show_question()
def show_correct(da):
    pravil.setText(da)
    start_test()
def check_answer(b):
    if knopki[0].isChecked() == True:
        show_correct('Правильно')
        b += 1
    else:
        show_correct('Неправельно')
def next_quetion(z):
    main_window.cur_question = main_window.cur_question + 1
    z += 1
    if main_window.cur_question == len(voprosi):
        main_window.cur_question = 0
        print_info(z, b)
    a = voprosi[main_window.cur_question]
    ask(a)
def print_info(z, b):
    print('Всего вопросов:', z)
    print('Правильных ответов:', b)
    print('Рейтинг:', b/z*100)





    
hline1 = QHBoxLayout()
vline2 = QVBoxLayout()
vline3 = QVBoxLayout()
vline2.addWidget(otvet1)
vline2.addWidget(otvet2)
vline3.addWidget(otvet3)
vline3.addWidget(otvet4)
hline1.addLayout(vline2)
hline1.addLayout(vline3)
RadioGroupBox.setLayout(hline1)
l = QHBoxLayout()
l.addWidget(RadioGroupBox)
question434 = QLabel('Какой национальности не существует?')
hline2 = QHBoxLayout()
hline2.addWidget(question434)
button = QPushButton('Ответить')
hline3 = QHBoxLayout()
hline3.addWidget(button)






Group = QGroupBox('Результат теста')
pravil = QLabel('Правильно/Неправельно')
pravilno = QLabel('Правильно')
line2 = QHBoxLayout()
line3 = QHBoxLayout()
line1 = QVBoxLayout()
line2.addWidget(pravil)
line3.addWidget(pravilno)
line1.addLayout(line2)
line1.addLayout(line3)
Group.setLayout(line1)
l2 = QHBoxLayout()
l2.addWidget(RadioGroupBox)
l2.addWidget(Group)
vline5 = QVBoxLayout()
vline5.addLayout(hline2)
vline5.addLayout(l2)
vline5.addLayout(hline3)
main_window.setLayout(vline5)
Group.hide()
RadioGroup = QButtonGroup()
RadioGroup.addButton(otvet1)
RadioGroup.addButton(otvet2)
RadioGroup.addButton(otvet3)
RadioGroup.addButton(otvet4)
button.clicked.connect(start_test)
next_quetion(z)


main_window.show()
app.exec_()
