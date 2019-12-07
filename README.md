# settings-gulp
<h1>Settings</h1>
  
git remote add origin git@github.com:matsevich/{repository-name}.git
git push -u origin master
_____________________________________________________________________
_____________________________________________________________________

___________________
#write in terminal#
___________________


npm install gulp -D
npx -p touch nodetouch gulpfile.js
npm install node-sass gulp-sass --save-dev
______________________________________________________________________
______________________________________________________________________



______________
#gulpfile.js#
______________

let gulp = require('gulp');
let sass = require('gulp-sass');

gulp.task('sass', function(){
    return gulp.src('sass/*.sass')
    .pipe(sass())
    .pipe(gulp.dest('css'))
});

gulp.task('html', function(){
    return gulp.src('**/*.html')
});

gulp.task('watch', function(){
    gulp.watch('sass/**/*.sass', gulp.parallel('sass'))
    gulp.watch('**/*.html', gulp.parallel('html'))
});
