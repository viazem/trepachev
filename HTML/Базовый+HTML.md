### Структура простой страницы

```
<!-- Это комментарий -->
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>Это заголовок страницы</title>
	</head>
	<body>
		Это основное содержимое страницы.
	</body>
</html>
```

### Основные теги HTML

Версия HTML (Пятая версия)

```
<!DOCTYPE html>
```

### Страница 

```
<html></html>
```

### Заголовок

```
<head></head>
```

### Основное содержимое страницы

```
<body></body>
```

### Внутри заголовка

Кодовая страница страницы

```
<meta charset="utf-8">
```

Заголовок страницы (на вкладке)

```
<title>Это заголовок страницы</title>
```

### Заголовок

```
<h1></h1>
<h2></h2>
<h3></h3>
```

### Параграф

```
<p></p>
```

### Толстый шрифт

```
<b></b>
```

### Наклонный шрифт

```
<i></i>
```

### Списки

Списки неупорядоченные

```
<ul></ul>
```

Списки упорядоченные

```
<ol></ol>
```

Содержание списков (внутри списков)

```
<li></li>
```

### Ссылки

Cсылки на сайты

```
<a href="https://www.google.com">Ссылка</a>
```

Внутренние ссылки

Между двумя файлами

```
file index.html

<h1>Index</h1>
<a href="page.html">link on Page</a>
```

```
file page.html

<h1>Page</h1>
<a href="index.html">link on Index</a>
```

### Работа с изображениями

```
<img src="smile.png">
```

### Ширина картинки

```
<img src="smile.png" width="100">
```

### Высота картинки

```
<img src="smile.png" height="100">
```

### Ширина и высота картинки

```
<img src="smile.png" width="100" height="70">
```

### Таблица

```
<table border="1">
	<!--Это будет первый ряд таблицы:-->
	<tr>
		<td>cell 1</td>
		<td>cell 2</td>
	</tr>

	<!--Это будет второй ряд таблицы:-->
	<tr>
		<td>cell 3</td>
		<td>cell 4</td>
	</tr>
</table> 
```

### Ширина и высота таблицы

```
<table border="1" width="300" height="200">
	...
</table>
```

### Ячейки-заголовки в таблице

```
<table border="1" width="300">
	<tr>
		<th>Name</th>
		<th>Surname</th>
		<th>Salary</th>
	</tr>
	<tr>
		<td>John</td>
		<td>Smith</td>
		<td>200$</td>
	</tr>
	...
</table>
```

