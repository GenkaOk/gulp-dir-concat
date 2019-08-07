Gulp Package for concatenation directories to one file for every directory

Fork from gulp-concat-dir

## Install
```sh
npm install gulp-dir-concat
```

## Example
```js
var gulp = require('gulp');
var concatDir = require('gulp-dir-concat');

gulp.task('concat',function(){
	return gulp
		.src('js/**/*.js')
		.pipe(concatDir())
		.pipe(gulp.dest('build/js'));
});
```

## Options

### options.appendName
``options.appendName`` - String append filename. For example: 
```js
gulp.task('concat',function(){
	return gulp
		.src('js/**/*.js')
		.pipe(concatDir({appendName: '.min.js'}))
		.pipe(gulp.dest('build/js'));
});
``` 
Directories: ``js/app/`` ``js/libs/``

Return: ``build/js/app.min.js`` ``build/js/libs.min.js``

___

### options.prependName
```options.prependName``` - String prepend filename. For example:
```js
gulp.task('concat',function(){
	return gulp
		.src('js/**/*.js')
		.pipe(concatDir({appendName: '.min.js', prependName: 'app.'}))
		.pipe(gulp.dest('build/js'));
});
``` 

Directories: ``js/main/`` ``js/libs/``

Return: ``build/js/app.main.min.js`` ``build/js/app.libs.min.js``