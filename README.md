# PHP Style Guide

## Table of contents
1. [Tabs](#tabs)
2. [Whitespace](#whitespace)
3. [Commas](#commas)
4. [Naming conventions](#naming-conventions)
5. [Classes](#classes)
6. [Accessors](#accessors)
7. [Strings](#strings)
8. [Functions](#functions)
9. [Comparison Operators & Equality](comparison-operators--equality)
10. [Blocks](#block)
11. [Comments](#comments)

### Tabs
- [1.1](#1.1) Use soft spaces instead of tabs.
- [1.2](#1.2) Use an intendation of 4 spaces.

**[⬆ back to top](#table-of-contents)**


### Whitespace
- [2.1](#2.1) Place one space before the leading brace.
```php
  class Person {
      public function __contruct() {}
  }
```

- [2.2](#2.2) Place one space before the opening paranthesis in control statements (`if`, `while` etc.)
```php
  if ( person->name === 'John Doe' ) {}
```

- [2.3](#2.3) Place no space before the argument list in function calls and declarations.
```php
  class Person {
      public function __contruct() {}

      /**
       * Walks the line.
       *
       * @return void
       */
      public function walkTheLine() {
          echo 'I am walking the line.';
      }
  }
  
  $person = new Person();
  $person->walkTheLine();
```

- [2.4](#2.4) Set off operators with spaces.
```php
  $x = 1 + 2;
```

- [2.5](#2.5) Use indentation when making long method chains. Use a leading arrow, which emphasizes that the line is a method call, not a new statement.
```php
  $person->walkTheLine()
         ->jump();
```

- [2.6](#2.6) Place one space at the start and one space at the end inside the argument list in function calls and declarations.
```php
  class Person {
      public function __contruct() {}

      /**
       * Walks the line for a given amount of meters.
       *
       * @param int $meters Meters to walk
       * @return void
       */
      public function walkTheLine( $meters ) {
          echo 'I am walking the line for ' . $meters . 'm.';
      }
  }
  
  $person->walkTheLine( 500 );
```

- [2.7](#2.7) Place one space at the start and one space at the end inside the braces in control statements (`if`, `while` etc.)
```php
  if ( person->name === 'John Doe' ) {
      $person->walkTheLine( 500 );
  }
```

- [2.8](#2.8) Do not allign assignments.
```php
  // Don't do this
  $name   = 'John Doe';
  $age    = 22;
  $region = 'Hessen';
  
  // Correct way
  $name = 'John Doe';
  $age = 22;
  $region = 'Hessen';
```

- [2.8](#2.8) Also not in arrays.
```php
  // Don't do this
  $personProperties = array(
      'name'      => 'John Doe',
      'age'       => 22,
      'region'    => 'Hessen',
  );
  
  // Correct way
  $personProperties = array(
      'name' => 'John Doe',
      'age' => 22,
      'region' => 'Hessen',
  );
```

**[⬆ back to top](#table-of-contents)**


### Commas
- [3.1](#3.1) Use trailing commas.
```php
  $numbers = array(
      1,
      2,
      3,
  );
```

- [3.2](#3.2) Use additional trailing commas in arrays.
```php
  $numbers = array(
      1,
      2,
      3, // additional trailing comma
  );
```

**[⬆ back to top](#table-of-contents)**


### Naming conventions
- [4.1](#4.1) Use camelCase when naming objects, functions, variables, and instances.
```php
  $firstName = 'John';
  function createPerson() {}
```

- [4.2](#4.2) Use SNAKE_CASE and uppercase for constants.
```php
  define( 'API_URL', '/api' );
```

- [4.3](#4.3) Use PascalCase when naming classes.
```php
  class SuperHero {
      public function __construct() {}
  }
```

- [4.4](#4.4) Don't use reserved words.
```php
  // bad
  $return = 42;
  
  // good
  $result = 42;
```

**[⬆ back to top](#table-of-contents)**


### Classes
- [5.1](#5.1) Use arrow notation when accessing properties or methods.
```php
  $person->walkTheLine();
```

- [5.2](#5.2) Use subscript notation `[]` when accessing properties with a variable.
```php
  $propertyName = 'origin';
  $origin = $person[$propertyName];
```

- [5.3](#5.3) Always write out property and method visibility.
```php
  // bad
  class Person {
      function __construct() {}
  }
  
  // good
  class Person {
      public function __construct() {}
  }
```

- [5.4](#5.4) **Note:** Take a look at [PHP5 visibility](http://php.net/manual/en/language.oop5.visibility.php).

**[⬆ back to top](#table-of-contents)**


### Accessors
- [6.1](#6.1) Accessor functions for properties are not required.

- [6.2](#6.2) If you do make accessor functions use `getVal()` and `setVal( 'hello' )`.
```php
  class Person {
      /**
       * @var string
       */
      private $name = '':
  
      public function __contruct() {}

      /**
       * Setter method for $name property
       *
       * @param string $name Name to assign
       * @return void
       */
      public function setName( $name ) {
          $this->name = $name;
      }
  }
```

- [6.3](#6.3) If the property is a `boolean`, use `isVal()` or `hasVal()`.
```php
  if ( $person->hasCoffee() ) {}
  if ( $person->isAlive() ) {}
```

- [6.4](#6.4) It's okay to create `get()` and `set()` functions, but be consistent.
```php
  class Person {
      /**
       * @var string
       */
      private $name = '':
  
      public function __contruct() {}

      /**
       * Setter method for the property passed in $key parameter.
       *
       * @param string $key Property that should be assigned
       * @param mixed $val Value to assign
       * @return void
       */
      public function set( $key, $val ) {
          $this[$key] = $val;
      }

      /**
       * Getter method for the property passed in $key parameter.
       *
       * @param string $key Property to get
       * @return mixed
       */
      public function get( $key ) {
          return $this[$key];
      }
  }
  
  $person = new Person();
  $person->set( 'name', 'John Doe' );
```

**[⬆ back to top](#table-of-contents)**


### Strings
- [7.1](#7.1) Use single quotes `''` for strings.
```php
  $person->name = 'John Doe';
```

- [7.2](#7.2) Strings longer than 110 characters should be written across multiple lines using string concatenation.
```php
  $person->description = 'I'm a very long text and need to be written across multiple lines using string ' .
      'concatenation.';
```

- [7.3](#7.3) When programmatically building up strings, use sprintf instead of concatenation.
```php
  $lastName = 'Doe';
  $person->name = sprintf( 'John %s', $lastName );
```

**[⬆ back to top](#table-of-contents)**


### Functions
- [8.1](#8.1) Never declare a function in a non-function block (if, while, etc).
```php
  // Don't do this!
  if ( $isTrue ) {
      function createPerson() {}
  }
```

- [8.2](#8.2) Use default parameter syntax rather than mutating function arguments.
```php
  function createPerson( $name = '' ) {}
```

**[⬆ back to top](#table-of-contents)**


### Comparison Operators & Equality
- [9.1](#9.1) Use `===` and `!==` over `==` and `!=`.

- [9.2](#9.2) Use shortcuts.
```php
  // Use
  if ( $person->cars ) {}
  
  // Rather then
  if ( !empty( $person->cars ) ) {}
```

- **Note:** For more information see [Type Comparisons](http://php.net/manual/en/types.comparisons.php).

**[⬆ back to top](#table-of-contents)**


### Blocks
- [10.1](#10.1) Use braces with all multi-line blocks.
```php
  if ( !$person->age ) return false; 
  // or
  if ( !$person->age ) {
      return false;
  }
  
  // but NOT
  if ( !$person->age ) { return false; }
  // or
  if ( !$person->age )
      return false;
```

- [10.2](#10.2) If you're using multi-line blocks with if and else, put else on the same line as your if block's closing brace.
```php
  if ( $person->cars ) {
      echo 'Nice cars!';
  } else {
      echo 'Riding bike?';
  }
```

**[⬆ back to top](#table-of-contents)**


### Comments
- [11.1](#11.1) Use `/** ... */` for multi-line comments. Include a description, specify types and values for all parameters and return values.
```php
  class Person {
      public function __contruct() {}

      /**
       * Walks the line for a given amount of meters.
       *
       * @param int $meters Meters to walk
       * @return void
       */
      public function walkTheLine( $meters ) {
          echo 'I am walking the line for ' . $meters . 'm.';
      }
  }
```

- [11.2](#11.2) **Note:** For more information see [phpDocumentor](http://www.phpdoc.org/docs/latest/index.html).

- [11.3](#11.3) Use `#` for single line comments. Place single line comments on a newline above the subject of the comment. Put an empty line before the comment.
```php
  echo 'Look at dat comment';
  
  # Create a new person
  $person = new Person();
```

- [11.4](#11.4) Use `# FIXME:` to annotate problems.
```php
  # FIXME: Something is wrong here, please fix it
```

- [11.5](#11.5) Use `# TODO:` to annotate solutions to problems.
```php
  # TODO: Write more code!
```

**[⬆ back to top](#table-of-contents)**