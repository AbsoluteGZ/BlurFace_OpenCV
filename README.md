# Размытие лиц на изображении с сохранением глаз

Этот скрипт размывает лица на изображении, используя библиотеку OpenCV, при этом сохраняя видимыми глаза.

![image](https://github.com/AbsoluteGZ/BlurFace_OpenCV/assets/110157963/300e018f-2812-47e9-a414-e5d9e9fef4af)


## Зависимости

Для работы скрипта необходимы следующие библиотеки:

```bash
pip install opencv-python matplotlib gdown
```

## Загрузка изображения

Скрипт загружает изображение с помощью `gdown` из указанного URL.  Замените URL на нужный вам адрес, если нужно обработать другое изображение.

```python
gdown.download('https://www.intermedia.ru/img/news_x400/386271.jpg', None, quiet=True)
```

## Обнаружение лиц и глаз

Используются каскадные классификаторы Haar для обнаружения лиц и глаз.  Классификаторы уже включены в OpenCV.

## Размытие лиц

Функция `blur_face` размывает лицо с помощью Гауссова размытия.  Для сохранения глаз создается эллиптическая маска, которая затем модифицируется путем вырезания кругов, соответствующих обнаруженным глазам. Размытие применяется только к области внутри маски, за исключением областей глаз.

## Визуализация результатов

Результат отображается с помощью Matplotlib, показывая исходное и обработанное изображения рядом.


##  Возможные улучшения

* **Более точное обнаружение глаз:**  Использование более совершенных методов обнаружения глаз или более точная настройка параметров каскадного классификатора глаз.
* **Различные методы размытия:**  Экспериментирование с различными методами размытия (например, медианное размытие).
* **Адаптация к различным размерам лиц:**  Улучшение обработки лиц разных размеров и ориентаций.
* **Обработка нескольких лиц:**  Код уже обрабатывает несколько лиц, но его можно оптимизировать для повышения производительности при большом количестве лиц на изображении.
* **Настраиваемые параметры размытия:** Добавление возможности настройки параметров Гауссова размытия (размер ядра).
* **Обработка ошибок:** Добавление обработки исключений для ситуаций, когда лица или глаза не обнаружены.
