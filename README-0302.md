# Задание по теме "Способы вызова функции"

import re  # Модуль для работы с шаблонами


def send_email(message, recipient, *, sender='university.help@gmail.com'):
    # Определяем шаблон адреса электронной почты
    email_pattern = r'(^\S+@\S+\.[ru|com|net]+$)'
    # Проверка на соответствие шаблону адресов эл.почты отправителя и получателя
    if re.match(email_pattern, sender) and re.match(email_pattern, recipient):
        # Проверяем, что адреса эл.почты отправителя и получателя НЕ совпадают
        if sender != recipient:
            # Проверяем, что адрес эл.почты отправителя совпадает с адресом по умолчанию
            if sender == 'university.help@gmail.com':
                print('Письмо успешно отправлено с адреса', sender, 'на адрес', recipient)
            else:
                print('НЕСТАНДАРТНЫЙ ОТПРАВИТЕЛЬ! Письмо отправлено с адреса', sender, 'на адрес', recipient)
        else:
            print('Нельзя отправить письмо самому себе!')
    else:
        print('Невозможно отправить письмо с адреса', sender, 'на адрес', recipient)


send_email('Это сообщение для проверки связи', 'vasyok1337@gmail.com')
send_email('Вы видите это сообщение как лучший студент курса!', 'urban.fan@mail.ru', sender='urban.info@gmail.com')
send_email('Пожалуйста, исправьте задание', 'urban.student@mail.ru', sender='urban.teacher@mail.uk')
send_email('Напоминаю самому себе о вебинаре', 'urban.teacher@mail.ru', sender='urban.teacher@mail.ru')
print()
send_email('Проверка связи', 'vasyok1337@gmail.com.uk')
send_email('Проверка связи', 'vasyok1337@gmail.com', sender='urban.info@gmail.net.uz')
