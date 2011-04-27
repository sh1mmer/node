## Assert

This module is used for writing unit tests for your applications, you can
access it with `require('assert')`.

**Module Methods**

### assert.fail(actual, expected, message, operator)

#### Arguments
_actual_: `mixed` Actual value to evaluate
_expected_: `mixed` Expected value to compare actual value to
_message_: `string` Exception message
_operator_: `string` The operator used to compare actual and expected
values

#### Return value
Does not return a value

#### Throws
`AssertionError`

#### Description
Fail always throws an AssertionError using the provided arguments

### assert.ok(value, [message])

#### Arguments
_value_: `mixed` Actual value to evaluate
_message (optional)_: `string` Exception message

#### Return value
Does not return a value

#### Throws
`AssertionError` 

#### Description
Tests if value is a `true` value, it is equivalent to `assert.equal(true, value, message);`

### assert.equal(actual, expected, [message])

#### Arguments
_actual_: `mixed` Actual value to evaluate
_expected_: `mixed` Expected value to compare actual value to
_message (optional)_: `string` Exception message

#### Return value
Does not return a value

#### Throws
`AssertionError` 

#### Description
Tests shallow, coercive equality with the equal comparison operator ( `==` ).

### assert.notEqual(actual, expected, [message])

#### Arguments
_actual_: `mixed` Actual value to evaluate
_expected_: `mixed` Expected value to compare actual value to
_message (optional)_: `string` Exception message

#### Return value
Does not return a value

#### Throws
`AssertionError` 

#### Description
Tests shallow, coercive non-equality with the not equal comparison operator ( `!=` ).

### assert.deepEqual(actual, expected, [message])

#### Arguments
_actual_: `mixed` Actual value to evaluate
_expected_: `mixed` Expected value to compare actual value to
_message (optional)_: `string` Exception message

#### Return value
Does not return a value

#### Throws
`AssertionError` 

#### Description
Tests for deep equality.

### assert.notDeepEqual(actual, expected, [message])

#### Arguments
_actual_: `mixed` Actual value to evaluate
_expected_: `mixed` Expected value to compare actual value to
_message (optional)_: `string` Exception message

#### Return value
Does not return a value

#### Throws
`AssertionError` 

#### Description
Tests for any deep inequality.

### assert.strictEqual(actual, expected, [message])

#### Arguments
_actual_: `mixed` Actual value to evaluate
_expected_: `mixed` Expected value to compare actual value to
_message (optional)_: `string` Exception message

#### Return value
Does not return a value

#### Throws
`AssertionError` 

#### Description
Tests strict equality, as determined by the strict equality operator ( `===` )

### assert.notStrictEqual(actual, expected, [message])

#### Arguments
_actual_: `mixed` Actual value to evaluate
_expected_: `mixed` Expected value to compare actual value to
_message (optional)_: `string` Exception message

#### Return value
Does not return a value

#### Throws
`AssertionError` 

#### Description
Tests strict non-equality, as determined by the strict not equal operator ( `!==` )

### assert.throws(block, [error], [message])

#### Arguments
_block_: `function` Code to be executed to throw an error (or not) wrapped in a
function
_error_: `Object`|`RegExp`|`function` Object constructor, regular
expression or function that will match the error being tested for 
_message (optional)_: `string` Exception message

#### Return value
Does not return a value

#### Throws
`AssertionError` 

#### Description
Expects `block` to throw an error. `error` can be constructor, regexp or 
validation function.

Validate instanceof using constructor:

    assert.throws(
      function() {
        throw new Error("Wrong value");
      },
      Error
    );

Validate error message using RegExp:

    assert.throws(
      function() {
        throw new Error("Wrong value");
      },
      /value/
    );

Custom error validation:

    assert.throws(
      function() {
        throw new Error("Wrong value");
      },
      function(err) {
        if ( (err instanceof Error) && /value/.test(err) ) {
          return true;
        }
      },
      "unexpected error"
    );

### assert.doesNotThrow(block, [error], [message])

#### Arguments
_block_: `function` Code to be executed to throw an error (or not) wrapped in a
function
_error_: `Object`|`RegExp`|`function` Object constructor, regular
expression or function that will match the error being tested for 
_message (optional)_: `string` Exception message

#### Return value
Does not return a value

#### Throws
`AssertionError` 

#### Description
Expects `block` not to throw an error, see assert.throws for details.

### assert.ifError(value)

#### Arguments
_value_: *mixed* A false value, e.g. err in a callback

#### Return value
Does not return a value

#### Throws
`AssertionError` 

#### Description
Tests if value is not a false value, throws if it is a true value. Useful when
testing the first argument, `error` in callbacks.


**Module Exception**

### AssertionError

#### Methods
_toString()_: String serialization

#### Inherits
`Error`

#### Properties
_name_: `string` Always "AssertionError"
_message_: `string` Exception message
_actual_: `mixed` Value generated during assertion test
_expected_: `mixed` Value to test assertion against
_operator_: `string` Operator used to compare values
_startStackFunction_: `function` Function in which exception was thrown
