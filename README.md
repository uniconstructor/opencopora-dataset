# opencopora-dataset

Архив с датасетом находится по ссылке: https://drive.google.com/open?id=1d-NZaK-9EUGM9QtfSYZCQ9tM1BlTjUhm

Обучающая выборка текстов opencorpora.org для разбиения текста на предложения

Ссылка на дамп базы данных, на основе которого создана выборка: http://opencorpora.org/?page=downloads

## Структура папок

Каждая папка в датасете соответствует одной записи в таблице books. Имя - поле book_id.

Каждая папка хранит данные одного документа:
* <book_id>-sentences.csv - список всех предложений документа (составлен вручную)
* <book_id>-text.txt - текст документа, составленный из предложений
* <book_id>-original.html - сохраненная копия веб-страницы из которой был извлечен текст (если есть)
* <book_id>-annotations.xml - полная разметка документа в формате opencopora. Описание формата можно посмотреть здесь: http://opencorpora.org/?page=export

## Обучающая выборка и предобученные модели для библиотеки sentencepiece

Для разбиения текста на предложения используется библиотека sentencepiece: https://github.com/google/sentencepiece

Документация по python-обертке: https://github.com/google/sentencepiece/blob/master/python/README.md

В корне проекта находится список файлов для нее:
* train.txt - обучающая выборка для токенизатора: предстваляет собой текстовый файл в котором собраны все предложения из базы opencopora (каждое предложение с новой строки)
* m.model - предобученная модель для разбиения текста на предложения
* m.vocab - словарь токенизатора sentencepiece (подробнее: https://github.com/google/sentencepiece#vocabulary-restriction)  и 
