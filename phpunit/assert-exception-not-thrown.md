## Assert that an exception is _not_ thrown in a PHPUnit test

While asserting an exception to be thrown in a PHPUnit test is straightforward, the opposite is a bit more difficult: asserting that a specific exception is _not_ thrown.

By wrapping the code potentially throwing the exception in a try/catch statement, it becomes possible to assert that the variable meant for holding the exception remains uninitialized. If the exception gets thrown, it will be assigned to the variable, causing the assertion to fail.

### Example
```php
try {
    // Test code potentially throwing a RuntimeException goes here
} catch (\RuntimeException $e) {}
$this->assertNull($e);
```
