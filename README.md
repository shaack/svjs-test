# svjs-test
Allows unit testing of ES6 modules without additional dependencies right in your browser.

Demo: [http://shaack.com/projekte/svjs-test/test/](http://shaack.com/projekte/svjs-test/test/)

## Works like this

- Create `test/index.html`:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Tests</title>
</head>
<body>
<script type="module">
    import {TestMyModule} from "./TestMyModule.js"
    TestMyModule.run();
</script>
</body>
</html>
```
- Create `TestMyModule.js`:

```
import {Test} from "../src/svjs/Test.js"

export class TestMyModule.js extends Test {

    testThisWillNotFail() {
        Test.assert(true);
    }

    testThisWillFail() {
        Test.assertEquals(42, 1 + 2);
    }

}
```

Just extend `Test`. 

Functions named `test...` will be executed automaticly, when you call 
`test/index.html` in your Browser.

## Result

The result will look like this:

![Test Result](http://shaack.com/projekte/assets/img/svjs_test.png)

## Why this one

You can test vanilla ES6 right in you browser, without Babel or other external dependencies. 