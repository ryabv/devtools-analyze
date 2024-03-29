# Использование браузерных DevTools - анализ сайта


## Network

На страницу загружается файл style.min.css?ver=17, однако при просмотре файла оказывается, что он не минифицирован.

*Файл в панеле Network*
![Файл в панеле Network](./screenshots/style-min-css-ver-17.png "Файл в панеле Network")

*Файл в панеле Source*
![Файл в панеле Source](./screenshots/style-min-css-ver-17-source.png "Файл в панеле Source")

При проверке на замедленной скорости самым медленным элементом была  картинка размером 2500 на 1250 пикселей, которая подгружалась в окно размером 630 на 135 пикселей. Более того, картинка не была минифицирована. Для теста я закинул файл в минификатор <a href="https://tinypng.com/" target="_blank">TinyPNG</a>, который показал, что простая минификация уменьшает размер картинки на более, чем 70%, с 420 КБ до 122 КБ.

*Партнёрский материал во вкладке Network*
![adfox-adx](./screenshots/bonus-2-1.png "adfox-adx")

*Результат минификатора*
![adfox-adx](./screenshots/bonus-2-1-1.png "adfox-adx")

*Партнёрский материал на сайте*
![adfox-adx](./screenshots/bonus-2-1-2.png "adfox-adx")


### Дублированная загрузка файлов

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

<table>
	<tr>
		<th>Событие</th>
		<th>Базовые настройки</th>
		<th>Slow 3G & CPU 4x slowdown</th>
	</tr>
	<tr>
		<td>First Paint</td>
		<td align="right">1 691 ms</td>
		<td align="right">14 454 ms</td>
	</tr>
	<tr>
		<td>First Meaningful Paint</td>
		<td align="right">2 858 ms</td>
		<td align="right">21 171 ms</td>
	</tr>
	<tr>
		<td>DOM Content Loaded</td>
		<td align="right">4 267 ms</td>
		<td align="right">34 167 ms</td>
	</tr>
	<tr>
		<td>Load</td>
		<td align="right">7 400 ms</td>
		<td align="right">62 346 ms</td>
	</tr>
</table>

Сколько времени тратится на разные этапы обработки документа:

<table>
	<tr>
		<th>Этап обработки</th>
		<th>Базовые настройки</th>
		<th>Slow 3G & CPU 4x slowdown</th>
	</tr>
	<tr>
		<td>Loading</td>
		<td align="right">201 ms</td>
		<td align="right">372 ms</td>
	</tr>
	<tr>
		<td>Scripting</td>
		<td align="right">4 808 ms</td>
		<td align="right">12 389 ms</td>
	</tr>
	<tr>
		<td>Rendering</td>
		<td align="right">1 536 ms</td>
		<td align="right">9 416 ms</td>
	</tr>
	<tr>
		<td>Painting</td>
		<td align="right">370 ms</td>
		<td align="right">1 324 ms</td>
	</tr>
</table>


## Coverage

<details>
	<summary>Скриншот вкладки</summary>
	<img src="./screenshots/tab-screenshot.png" alt="Скриншот вкладки">
</details>

Объём неиспользованных файлов в ходе загрузки страницы:

<table>
	<tr>
		<th rowspan="2">Тип</th>
		<th colspan="2">Базовые настройки</th>
		<th colspan="2">Slow 3G & CPU 4x slowdown</th>
	</tr>
	<tr>
		<th>Объём, KB</th>
		<th>%</th>
		<th>Объём, KB</th>
		<th>%</th>
	</tr>
	<tr>
		<td>CSS</td>
		<td align="right">228 / 252</td>
		<td align="right">91%</td>
		<td align="right">228 / 252</td>
		<td align="right">91%</td>
	</tr>
	<tr>
		<td>CSS+JS</td>
		<td align="right">35 / 77</td>
		<td align="right">46%</td>
		<td align="right">24 / 53</td>
		<td align="right">45%</td>
	</tr>
	<tr>
		<td>JS</td>
		<td align="right">2 356 / 3 789</td>
		<td align="right">62%</td>
		<td align="right">1 898 / 2 869</td>
		<td align="right">66%</td>
	</tr>
	<tr>
		<td><b>Всего</b></td>
		<td align="right"><b>2 619 / 4 118</b></td>
		<td align="right"><b>64%</b></td>
		<td align="right"><b>2 150 / 3 174</b></td>
		<td align="right"><b>66%</b></td>
	</tr>
</table>