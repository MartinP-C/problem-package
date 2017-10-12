## Problem
If I `npm install` the not working packages when I open VSCode - eslint throws an error:  
`Configuration for rule "no-console" is invalid: Severity should be one of the following: 0 = off, 1 = warning, 2 = error (you passed "off").`  
Seen in the ESLint output on the panel if you don't get the popup.  
Then linting stops for all js files.  
Far as I can tell that rule config from the error is in a node\_module but supposedly ESLint in VSCode doesn't check node_modules files.  
And to make it better.  
When writing this up I actually got the error on a different rule!!  
`Configuration for rule "indent" is invalid: Severity should be one of the following: 0 = off, 1 = warning, 2 = error (you passed "error").` 
  
If I have the original packages installed it doesn't.
If I install individually the additions (see ++ in diff) then I don't get the error.  
It only seems to happen if I `npm install` to do all at once??  
  
It must(!) be something in `node_modules` because it goes away when I delete the folder.  
Can you repeat this? Can you work out where the error is coming from?  
Annoying me a lot now.

## Original package
{   
    "browser-sync": "^2.10.1",
    "del": "^2.2.0",
    "gulp": "^3.9.0",
    "gulp-autoprefixer": "^3.1.0",
    "gulp-cache": "^0.4.1",
    "gulp-concat": "^2.6.0",
    "gulp-csso": "^1.0.1",
    "gulp-eslint": "^1.1.1",
    "gulp-html": "^0.4.4",
    "gulp-htmlmin": "^1.3.0",
    "gulp-imagemin": "^2.4.0",
    "gulp-sass": "^2.1.1",
    "gulp-uglify": "^1.5.1"
}

## New not working package
{
    "babel-core": "^6.26.0",
    "babel-preset-env": "^1.6.0",
    "browser-sync": "^2.10.1",
    "del": "^2.2.0",
    "eslint-codeframe-formatter": "^1.0.2",
    "gulp": "^3.9.0",
    "gulp-autoprefixer": "^3.1.0",
    "gulp-babel": "^7.0.0",
    "gulp-cache": "^0.4.1",
    "gulp-concat": "^2.6.0",
    "gulp-csso": "^1.0.1",
    "gulp-eslint": "^1.1.1",
    "gulp-htmlhint": "^0.3.1",
    "gulp-htmlmin": "^1.3.0",
    "gulp-imagemin": "^2.4.0",
    "gulp-sass": "^2.1.1",
    "gulp-sourcemaps": "^2.6.1",
    "gulp-uglify": "^1.5.1"
}

### Diff
{
    ++ "babel-core": "^6.26.0",
    ++ "babel-preset-env": "^1.6.0",
    ++ "eslint-codeframe-formatter": "^1.0.2",
    ++ "gulp-babel": "^7.0.0",
    -- "gulp-html": "^0.4.4",
    ++ "gulp-htmlhint": "^0.3.1",
    ++ "gulp-sourcemaps": "^2.6.1"
}
