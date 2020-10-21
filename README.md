# CBER Web Development Notes

This repository was set up to collect important general information and issues related to the web development work at
the [Ball State University Center for Business and Economic Research](http://bsu.edu/cber). 

If there are any issues that apply to a large number of CBER's websites or none of them in particular, 
they should go here. 

## Services
All websites need the following:
 - A [GitHub](https://github.com) repo under the [BallStateCBER](https://github.com/BallStateCBER) organization
 - Unit testing and code sniffing with [Travis CI](https://travis-ci.com/)) (with a badge in`README.md`)
 - Testing with [Code Climate](https://codeclimate.com/) (with badges in `README.md`)
 - GitHub, Travis, and CodeClimate events in the `#webdev` channel of [cber.slack.com](https://cber.slack.com)

## Frameworks
 - [CakePHP 4.x](https://book.cakephp.org/4.0/en/index.html)
 - [Bootstrap 4.x](https://getbootstrap.com/)

## PHP standards 
 - [CakePHP code sniffer standards](https://github.com/cakephp/cakephp-codesniffer) (extension of [PSR-12](https://www.php-fig.org/psr/psr-12/))  
 - Test with [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)
 - Use camelCaps for variable names instead of underscored_names
 - Avoid prefixing method names with underscores
 - Store sensitive information (and information that changes based on environment) 
   in `.env` or `config/app_local.php` files that are not committed
 - Indent with four spaces
 - Avoid using any deprecated code from libraries (so migrating to the next major version will be easier)

## HTML standards
 - [HTML5](https://www.w3.org/TR/html5/) 
 - Test with [W3C Markup Validation Service](https://validator.w3.org/)
 - Where possible, hyphenate class names and element IDs instead of using underscores or camelCaps
 - Indent with four spaces

## Template file standards
 - Use short echo tags when not in a multiple-line block of code, e.g.
 
   ```html
    <a href="<?= $url ?>">
        <?= $label ?>
    </a>
   ```
   or
   ```html
    <a href="http://example.com">
        <?php
            $foo = getFoo();
            $bar = getBar($foo);
            echo ucwords($bar);
        ?>
    </a>
   ```
 - Declare `$this` and other variables in opening doc comment, e.g. 
   ```php
   <?php
       /**
        * @var \App\View\AppView $this
        * @var \App\Model\Entity\Survey $survey
        * @var \App\Model\Entity\Community $community
        */
   ?>
   ```
   Some of these can be automatically added by [dereuromark/cakephp-ide-helper](https://github.com/dereuromark/cakephp-ide-helper/)

## CSS (and preprocessor) standards
 - [Google style guide](https://google.github.io/styleguide/htmlcssguide.html)  
 - Test with [W3C CSS Validation Service](https://jigsaw.w3.org/css-validator/)
 - [Sass](http://sass-lang.com/) for preprocessing

## JavaScript standards
 - [JavaScript Standard Style](https://standardjs.com/rules.html)
 - [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html) for any matter not covered by the 
   JavaScript Standard Style 
 - Lint with [ESLint](http://eslint.org/)
 - Avoid the use of [jQuery](https://jquery.com/) except when implementing jQuery plugins that have no practical vanilla 
   JS alternative

## Consideration for future standards
 - [Stickler CI](https://stickler-ci.com/)
 - [Webpack](https://webpack.js.org/)
 - [React](https://reactjs.org/)
 - [Babel](https://babeljs.io)
 - [TypeScript](https://www.typescriptlang.org/)
