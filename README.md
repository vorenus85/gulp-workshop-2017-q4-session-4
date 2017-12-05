# BrowserSync task with gulp
Work to the <b>start</b> folder, the solutions are in the <b>end</b> folder

## 1. Create browser-sync task

Declare the browserSync gulp package in your gulpfile.js

```
var browserSync = require('browser-sync').create();
```

install browser-sync through terminal
```$xslt
npm install browser-sync --save-dev
```

Extend the sass task at the end with browsersync.stream()

```
.pipe(browserSync.stream());
```

Extend the main-js task at the end with browserSync.stream()

```
.pipe(browserSync.stream());
```

Create the main browser-sync task
```
// browserSync
gulp.task('browserSync', function() {
   browserSync.init({
       server: {
           baseDir: '../' // the place where is index.html
       }
   });
  
   gulp.watch("scss/*.scss", ['sass']);
   gulp.watch("js/*.js", ['main-js']);
});
```

## 2. Default gulp task 
Create a default gulp task with browserSync

```
gulp.task('default', ['browserSync'], function (){   gulp.watch('../index.html', browserSync.reload);
});
```

## 3. Run default gulp task
gulp will automaticly open http://localhost:3000/ 

## 4. Find BrowserSny srcipt 
fid browserSync script by using devtools on out app

```$xslt
<script id="__bs_script__">//<![CDATA[
    document.write("<script async src='/browser-sync/browser-sync-client.js?v=2.18.13'><\/script>".replace("HOST", location.hostname));
//]]></script>
```

## 5. Modify style.scss
Modify ```$themeColor``` value to ```red``` <b>ses what happens</b>

## 6. Modify main.js
Modify your code in main.js

this section:

```$xslt
 $('#countdown_dashboard').countDown({
    targetDate: {
        'day':      30,
        'month':    12,
        'year':     2018,
        'hour':     23,
        'min':      59,
        'sec':      59,
    },
    omitWeeks: true
});
``` 

to this:

```$xslt
 $('#countdown_dashboard').countDown({
    targetDate: {
        'day':      30,
        'month':    12,
        'year':     2019,
        'hour':     23,
        'min':      59,
        'sec':      59,
    },
    omitWeeks: true
});
```

<b>see what happens</b>

## 7. Switch off browserSync

go to terminal hit ```CRTL+C``` then ```Y``` to terminate job


