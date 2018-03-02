#univalid-key-logger

Simple key logger and filters handler (sandbox) <br>
Univalid module dependency.


## Install

```sh
npm i univalid-key-logger
```


## Usage

```js
const UKL = require('univalid-key-logger');
const keyLogger = UKL();
```


## API


#### logXss(value)

Catch xss syntax 

**value** - Type `string`

```js
keyLogger.logXss('<mzf>');
```


#### test(value, tmp)

Tests the pattern matching.

**value** - Type `string`

**tmp** - Type `string`

In current moment available only "email" template

```js
keyLogger.test('test@mail.com', 'email');
```


#### applyFilter(filter, value)

Tests the pattern matching of symbols

**filter** - Type `string`

In current moment available patterns supporting "univalid-strategy-form" module:
* oL - only latin symbols
* oC - only cyrillic symbols
* oN - only numbers
* oP - only numbers and latin symbols

**value** - Type `string`

```js
keyLogger.applyFilter('oL', 'I am bored');
```


#### onFilter(event, filter)

Tests the pattern matching of symbols (by event)

**event** - Type `object` - native object of event

**filter** - Type `string`

In current moment available patterns supporting "univalid-strategy-form" module:
* oL - only latin symbols
* oC - only cyrillic symbols
* oN - only numbers
* oP - only numbers and latin symbols

```js
keyLogger.onFilter(e, 'oC');
```

## License

ISC©
