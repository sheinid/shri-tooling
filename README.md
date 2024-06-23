# Использование Chrome DevTools

## Вкладка Network

1. Записать и сохранить в [HAR архив](./www.rigla.ru.har) профиль загрузки ресурсов при открытии страницы
2. Неоптимальные места

Делается бесполезный пустой запрос, который вернет пустой ответ.
![alt text](image.png)

Очень много graphql запросов. Некоторые из них можно отложить, либо например сделать на сервере.
![alt text](image-2.png)

Есть ресурсы, которые загружаются не по http2.
![alt text](image-3.png)

Картинки можно сжать, либо перенести в современный формат для веб-изображений (webp).

![alt text](image-4.png)  
![alt text](image-7.png)

Очень большой файл со скриптом. Его можно разделить на несколько, чтобы ускорить изначальную загрузку.
![alt text](image-5.png)

Много сторонних скриптов.
![alt text](image-6.png)
![alt text](image-9.png)

Ресурсы блокируют загрузку страницы.
![alt text](image-8.png)

## Вкладка Performance

1. Записать и сохранить в файл [профиль загрузки страницы](./Trace-20240622T012309.json)
2. измерить время в миллисекундах от начала навигации до событий First Paint (FP), First Contentful Paint (FCP), Largest Contentful Paint (LCP), DOM Content Loaded (DCL), Load.

- First Paint - 735ms

  ![alt text](image-10.png)

- First Contentful Paint - 735ms

  ![alt text](image-11.png)

- Largest Contentful Paint - 2959ms

  ![alt text](image-12.png)

- DOM Content Loaded - 696ms

  ![alt text](image-13.png)

- Load - 1448ms

  ![alt text](image-14.png)

DOM-элемент, на котором происходит LCP:

![alt text](image-16.png)

Этот элемент в DOM:

![alt text](image-19.png)

Время на разные этапы рендера:

- Loading - 19ms
- Scripting - 2008ms
- Rendering - 497ms
- Painting - 494ms

![alt text](image-17.png)

## Вкладка Coverage

Вкладка Coverage после загрузки страницы.
![alt text](image-18.png)

Неиспользованный CSS в ходе загрузки страницы. 44.7 Кб
![alt text](image-20.png)

Неиспользованный JS в ходе загрузки страницы. 3591.4 Кб
![alt text](image-29.png)

## Performance с 4x CPU Slowdown и Slow 3G

Вкладки Coverage и Network не отличаются ничем, кроме времени загрузки страницы.

1. Записать и сохранить в файл [профиль загрузки страницы](./Trace-20240623T095835.zip) (файл был сжат, из-за ограничений Github на размер файла)
2. измерить время в миллисекундах от начала навигации до событий First Paint (FP), First Contentful Paint (FCP), Largest Contentful Paint (LCP), DOM Content Loaded (DCL), Load.

- First Paint - 24519ms

  ![alt text](image-22.png)

- First Contentful Paint - 24519ms

  ![alt text](image-23.png)

- Largest Contentful Paint - 116462ms

  ![alt text](image-25.png)

- DOM Content Loaded - 41630ms

  ![alt text](image-24.png)

- Load - 121155ms

  ![alt text](image-26.png)

DOM-элемент, на котором происходит LCP:

![alt text](image-27.png)

Этот элемент в DOM:

![alt text](image-19.png)

Время на разные этапы рендера:

- Loading - 364ms
- Scripting - 39366ms
- Rendering - 5189ms
- Painting - 3817ms

![alt text](image-28.png)
