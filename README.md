# ISI 

* Date:    December 28, 2020
* Author:  Jaime A. Rodriguez <hi.i.am.jaime@gmail.com>
* Version: 1.0
* License: http://opensource.org/licenses/MIT

Creates a configurable fixed ISI. It requires some simple configuration. Essentially you must:

* Add the .scss file
* Add the .tpl file
* Create a trait with the ISI content
* Attach the trail to your Model

## Usage

~~~ scss
    // Import the base styles to your SCSS file
    @import '../app/modules/isi/scss/isi'; 
~~~

~~~ html
    <!-- Include the .tpl file, probably in the footer -->
    {{ #include ../modules/isi/template/isi }}
~~~

~~~ php
    // Create a trait to use in your Model
    trait Isi {
      // You need both of these properties
      public $isiHeading = "Important Safety Information";
      public $isiBody    = "<p>Sample ISI content</p>";
    }
~~~

~~~ php
    // Add the trait to your Model
    namespace Model;

    use \Sleepy\MVC\Model;

    class Homepage extends Model {
        // add it with the "use" statement
        use Isi;

        public $title = "...";
        // ...
    }
~~~

## Changelog

### Version 1.0

* Initial build