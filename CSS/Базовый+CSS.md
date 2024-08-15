### Основы работы с языком CSS

Файл со стилями должен иметь расширение .css. Чтобы подключить такой файл к HTML странице, в теге head следует написать такую конструкцию:

```
<link rel="stylesheet" href="fileName.css">
```

```
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>This is the title</title>
		<link rel="stylesheet" href="styles.css">
	</head>
	<body>
		<p>
			This is a paragraph with text.
		</p>
	</body>
</html>
```

### Про центрирование

https://habr.com/ru/articles/348500/

https://skillbox.ru/media/code/vyravnivanie-po-tsentru-v-css-priyemy-svoystva-podvodnye-kamni/#stk-1


### Как работать с CSS

Каждому тегу в HTML соответствует так называемый селектор CSS.
После селектора следует ставить фигурные скобки, внутри которых следует писать CSS свойства.
Их следует писать в таком формате: имя свойства, потом двоеточие, потом значение этого свойства (например, свойство - это цвет, а "красный" - это значение). Потом нужно поставить точку с запятой и можно писать следующее свойство.

```
p {
	color: red;
}
```
