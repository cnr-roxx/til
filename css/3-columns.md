# 3 columns layout

## Constatnt side-columns width, flexible middle-column width

```
<!DOCTYPE html>
<html lang="pl">
	<head>
		<title>css fun: 3 columns, middle one with flexible width</title>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta name="description" content="">
		<meta name="author" content="">

		<style>
            #column-1 {
                background-color: red;
                float: left;
                width: 80px;
            }
            #column-2 {
                background-color: green;
            }
            #column-3 {
                background-color: blue;
                float: right;
                width: 100px;
            }
		</style>

	</head>
	<body>
        <div id="container">
            <div id='column-1'><a href="#">Link 1</a></div>
            <!-- Warning! Order of columns matters! Third column is defined BEFORE second one -->
            <div id='column-3'><a href="#">Link 3</a></div>
            <div id='column-2'><a href="#">Link 2</a></div>
        </div>
	</body>
</html>
```

## Constatn container width and columns width

```
<!DOCTYPE html>
<html lang="pl">
	<head>
		<title>css fun: 3 columns</title>
		<meta charset="utf-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<meta name="description" content="">
		<meta name="author" content="">

		<style>
            #container {
                width: 300px;
                margin: 0 auto;
            }
            #column-1 {
                background-color: red;
                float: left;
                width: 100px;
            }
            #column-2 {
                background-color: green;
                float: left;
                width: 100px;
            }
            #column-3 {
                background-color: blue;
                float: left;
                width: 100px;
            }
            .clear-float {
                clear: both;
            }
		</style>

	</head>
	<body>
        <div id="container">
            <div id='column-1'><a href="#">Link 1</a></div>
            <div id='column-2'><a href="#">Link 2</a></div>
            <div id='column-3'><a href="#">Link 3</a></div>
        </div>
        <div class="clear-float"></div>
	</body>
</html>
```


