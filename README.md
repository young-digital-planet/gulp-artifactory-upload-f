# gulp-artifactory-upload-f
Gulp plugin to deploy files to a JFrog Artifactory server.
Unlike gulp-artifactory-upload, doesn't crash on non-json artifactory answer.

```
npm install gulp-artifactory-upload-f --save-dev
```

Example usage

```
var artifactoryUpload = require('gulp-artifactory-upload-f');

gulp.task( 'deploy', function() {
	return gulp.src( 'test.zip' )
		.pipe( artifactoryUpload( {
				url: 'http://artifactory.server.com:8081/artifactory/libs-release-local',
				username: 'user', // optional
				password: 'password' // optional,
				rename: function( filename ) { return filename + "1"; } // optional
			} ) )
		.on('error', gutil.log);
} );
```

To create zip files, i would recommend archiver https://www.npmjs.com/package/archiver or gulp-zip for integration with gulp https://www.npmjs.com/package/gulp-zip

