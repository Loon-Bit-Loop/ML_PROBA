# Модель восстановления пунктуации и регистра для русского языка, а также определения эмоциональной окраски аудиофайла или текста

## Описание
На вход даётся аудиофайл, в котором определяется эмоциональная окраска, затем этот файл транскрибируется в текст, далее работает модель, которая способна расставлять точки, запятые и знаки вопроса; определять регистр - слово в нижнем регистре, слово с первой буквой в верхнем регистре, слово в верхнем регистре. Модель разработана для восстановления текста после распознавания речи, поэтому работает со строками в нижнем регистре. В основу модели легла sbert_large_nlu_ru. В качестве обучающих данных использованы текстовые расшифровки интервью.

## Как это работает

- Текст переводится в нижний регистр и разбивается на слова.
- Слова разделяются на токены.
- Модель предсказывает класс для каждого токена. Классификация на 12 классов: 3+1 знака препинания * 3 варианта регистра.
- Функция декодировки восстанавливает текст соответственно предсказанным классам.

### Требования
Необходимые библиотеки:
- speech_recognition
- torch
- aniemore
- transformers
- numpy
- argparse
- distutils



![Описание](https://github.com/Loon-Bit-Loop/BigModels/blob/main/%D0%9A%D0%B8%D0%BB%D0%BB%D0%B5%D1%80-%D1%84%D0%B8%D1%87%D0%B8/sbert_punc_case_ru/screen/demo1.png)

Результат работы модели

<a href='https://drive.google.com/file/d/1LoHC3pD3tXHqni0EbGDjKayj-P8cZWt4/view?usp=sharing'> Скачайте</a> модель из Google Drive и поместите в папку проекта.
Запустите файл playing_with_model.py:
