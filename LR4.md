# Лабораторная работа №4

Цель работы: Изучить принципы работы unit тестов.

Теоретическая часть: 

Модуль unittest предоставляет богатый набор инструментов для написания и запуска тестов. Однако достаточно лишь некоторых из них, чтобы удовлетворить потребности большинства пользователей.

```python
import unittest

class TestStringMethods(unittest.TestCase):

  def test_upper(self):
      self.assertEqual('foo'.upper(), 'FOO')

  def test_isupper(self):
      self.assertTrue('FOO'.isupper())
      self.assertFalse('Foo'.isupper())

  def test_split(self):
      s = 'hello world'
      self.assertEqual(s.split(), ['hello', 'world'])
      # Проверим, что s.split не работает, если разделитель - не строка
      with self.assertRaises(TypeError):
          s.split(2)

if __name__ == '__main__':
    unittest.main()
```

[Юнит-тесты на Python: Быстрый старт](https://habr.com/ru/company/otus/blog/481806/)

## Варианты заданий

Написать unit тесты для своих вариантов из лабораторной работы №3.
