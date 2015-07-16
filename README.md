# PHP Style Guide

## Table of contents
1. [Tabs](#tabs)
2. [Whitespace](#whitespace)
3. [Commas](#commas)
4. [Naming conventions](#naming-conventions)
5. [Classes](#classes)

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


### Classes
- [5.1](#5.1) Use arrow notation when accessing properties or methods.
```php
  $person->walkTheLine();
```

- [5.2](#5.2) Always write out property and method visibility.
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

- [5.3](#5.3) **Tip:** Take a look at [PHP5 visibility](http://php.net/manual/en/language.oop5.visibility.php).