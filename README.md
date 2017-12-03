"# gulp-workshop-2017-q4-session-4"

# 1. Create out browserSync task

Declare the browserSync gulp package in our gulpfile.js

```
var browserSync = require('browser-sync').create();
```

Extend the sass task with browsersync.stream()

```
.pipe(browserSync.stream());
```

Extend the main-js task with browserSync.stream()

```
.pipe(browserSync.stream());
```

Create the main browser-sync task
```
// browserSync
gulp.task('browserSync', function() {
   browserSync.init({
       server: {
           baseDir: '../'
       }
   });
  
   gulp.watch("scss/*.scss", ['sass']);
   gulp.watch("js/*.js", ['main-js']);
});
```

# 2. Create a default gulp task with browserSync

```
gulp.task('default', ['browserSync'], function (){   gulp.watch('../index.html', browserSync.reload);
});
```