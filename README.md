# Использование браузерных DevTools - анализ сайта


## Network

### На страницу загружается файл style.min.css?ver=17, однако при просмотре файла оказывается, что он не минифицирован.

*Файл в панеле Network*
![Файл в панеле Network](./screenshots/style-min-css-ver-17.png "Файл в панеле Network")

*Файл в панеле Source*
![Файл в панеле Source](./screenshots/style-min-css-ver-17-source.png "Файл в панеле Source")


### Дублированная загрузка файлов.

*zrt_lookup.html*
![zrt_lookup.html](./screenshots/2.png "zrt_lookup.html")

*show-ads-impl.js*
![show-ads-impl.js](./screenshots/2-1.png "show-ads-impl.js")

*render.html*
![render.html](./screenshots/2-2.png "render.html")

*osd.js*
![osd.js](./screenshots/2-3.png "osd.js")

*woff2*
![woff2](./screenshots/2-4.png "woff2")

*getCode*
![getCode](./screenshots/2-5.png "getCode")

*adsbygoogle.js*
![adsbygoogle.js](./screenshots/2-6.png "adsbygoogle.js")

*adfox-adx*
![adfox-adx](./screenshots/2-7.png "adfox-adx")


## Performance

Время от начала навигации до событий:

* **First Paint**: 1691.2 ms
* **First Meaningful Paint**: 2858 ms
* **DOM Content Loaded**: 4267.2 ms
* **Load**: 7399.6 ms

Сколько времени тратится на разные этапы обработки документа:

* **Loading**: 201 ms
* **Scripting**: 4808 ms
* **Rendering**: 1536 ms
* **Painting**: 370 ms