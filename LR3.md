# Лабораторная работа №3

Цель работы: Изучить принципы работы web - приложений.

Теоретическая часть: 

Flask — это микрофреймворк для создания простого и быстрого проекта на языке программирования Python с возможностью масштабирования до сложных приложений. Понятие «микрофреймворк» означает, что в комплекте нет набора инструментов и библиотек, программист может сам установить их в зависимости от задач.

```python
pip install flask
```

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello():
    return 'Hello, World!'
```

## Работа с шаблонами и формой в flask

Создаем HTML документ и форму в нем

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<form action="" method="post">
    <input type="text" name="num_1">
    <input type="text" name="num_2">
    <input type="submit">
</form>
<h1>{{ans}}</h1>
</body>
</html>
```

Обрабатываем данный формы в flask

```python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route('/')
@app.route('/index')
def index():
    return render_template("index.html")

@app.route('/', methods=['post', 'get'])
def form():
    if request.method == 'POST':
        num_1 = int(request.form.get('num_1'))
        num_2 = int(request.form.get('num_2'))
    return render_template('index.html', ans=num_1 + num_2)

if __name__ == '__main__':
    app.run()
```

[Мега-Учебник Flask, Часть 1: "Привет, Мир!"](https://habr.com/ru/post/193242/)

[Создание веб-приложения с помощью Flask в Python 3 | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-make-a-web-application-using-flask-in-python-3-ru#)

## Варианты заданий

1. Вычисление тригонометрических функций с заданной точностью, выбор градусов или радиан.
2. Объемы геометрических фигур с заданной точностью
3. Поиск самого частого слова в файле
4. Конвертер курсов валют
5. Ипотечный калькулятор
6. Нахождение корней квадратного уравнения
7. Создание страницы авторизации, логин пароль в файле и регистрация.
8. Сайт анкета с вопросами, запись в файл
9. Калькулятор сложного процента
