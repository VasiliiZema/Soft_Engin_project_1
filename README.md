# Практическая работа по программной инженерии

#### ***Студент: РИМ-130908 - Земов В.А.***

#### ***Цель проекта***

Разработать Web или API приложение машинного обучения и развернуть его в облаке. 
____
### Этап №1 - Применение модели машинного обучения (Translator_Ru_En.py)

Применена модель для перевода на английский язык текста написанного на русском языке.

Для данной задачи лучше всего подходит инструментарий "Hugging Face" с моделью перевода с русского на английский язык "Helsinki-NLP/opus-mt-ru-en".

~~~
#Устанавливаем библиотеку
#pip install transformers sentencepiece

from transformers import pipeline

#Сосзаем пайплан для модели перевода с русского на анлийский язык
classifier = pipeline(model="Helsinki-NLP/opus-mt-ru-en")

#Вводим текст на русском языке для обработки моделью!
text_eng = classifier(input())

#Выводим результат перевода на английском языке!
print(text_eng)
~~~

#### ***Применение:***

Введите текст в консоли на русском языке.

#### ***Результат:***

В консоли будет выведен текст на английском языке.
___
### Этап №2 - Разработка Web-приложения (WebTranslator_Streamlit.py)

-Разработано Web-приложение на основе библиотеки Streamlit -  https://streamlit.io, которое использует выбранную выше модель.

***Запуск приложения:*** 
~~~
streamlit run ./WebTranslator_Streamlit.py
~~~
___
### Этап №3 - Разработака API для приложения (Translator_ru_en_FastAPI.py)

-С помощью библиотеки FastAPI - https://fastapi.tiangolo.com разработано API для модели перевода на английский язык текста, написанного на русском языке.

***Запуск API приложения:***
~~~
uvicorn Translator_ru_en_FastAPI:app
~~~

-Для использования модели через API необходимо выполнить POST-запрос по соответствующему адресу, например:
~~~
curl -X 'POST' 'http://127.0.0.1:8000/predict/' -H 'Content-Type: application/json' -d '{"text": "Привет, Василий"}'
~~~

-Созданный файл requirements.txt содержит список всех библиотек, которые необходимо установить для работы API приложения машинного обучения. 

***Установка необходимых пакетов***
~~~
pip install -r requirements.txt
~~~
___
### Этап №4 - Развертывание Web приложения в облаке Streamlit (Link_to_the_application_in_streamlit)

Выполнено развертывание Web приложения в облаке Streamlit - https://streamlit.io/cloud для доступа пользователей через интернет.

Приложение доступно по ссылке - https://softenginproject1-webtranslator-ru-en-vasiliizema.streamlit.app/
___
### Этап №5 - тесты для API (test_API.py)

-Разработаны тесты для API(test_API.py) модели машинного обучения(Translator_ru_en_FastAPI.py). 

-Настроен автоматический запуск тестов при выполнении commit в репозиторий на GitHub.

