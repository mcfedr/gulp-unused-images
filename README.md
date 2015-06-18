# Unused Images

Attempts to list all the images that are not referenced in your html and css

## Usage

Stream all the images, css and html files that you have into it, it emits errors, so use plumber to catch and see them

	gulp.task('images:filter', function () {
	    return gulp.src(['app/images/**/*', '.tmp/styles/**/*.css', 'app/*.html', 'app/partials/**/*.html'])
	        .pipe(plumber())
	        .pipe(unusedImages())
	        .pipe(plumber.stop());
	});
	
## Output

The output lists the images that it found no references to and any ng-src attributes that it saw, allowing you to try and decided what that would refer to

    Error: Unused images: arrow_grey_right.png, bg-circel-not-empty-small.png
    ng-src: {{ app.iconUrl || 'images/generic_android_icon.png' }}
