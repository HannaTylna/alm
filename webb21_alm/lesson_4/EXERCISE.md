# Exercise 4

## Husky

1. Go to husky in npm [husky](https://www.npmjs.com/package/husky)
2. Go to their homepage [typicode husky](https://typicode.github.io/husky/#/)
3. Husky requires a git project, so create & clone a GitLab project named learn_husky
4. Initialize a node project with npm init

    ```bash
    npm init
    ```

5. To install husky you can do it Manually or Automatic read the docs. We will use the automatic version with npm

    ```bash
    npx husky-init && npm install
    git commit -m "test commit" # This will fail
    ```

6. Add a hello world text to husky

    ```bash
        npx husky add .husky/pre-commit "echo hello world"
        git commit -m "test to commit" # This will fail but hello world is not printed
    ```

    ```bash
        # If you have issues adding on windows, as a workaround try
        npx husky add .husky/pre-commit \"echo hello world\"
    ```

7. Modify the file .husky/pre-commit so the hello world text is printed before the npm test

   ```bash
    git commit -m "test commit"

    # hello world

    # > first_husky@1.0.0 test /Users/rober/repos/webb20/learn_husky
    # > echo "Error: no test specified" && exit 1

    # Error: no test specified
    # npm ERR! Test failed.  See above for more details.
    # husky - pre-commit hook exited with code 1 (error)
   ```

8. Remove the hello world text
9. Modify the text written by npm test in your package.json

### Mocha

1. In the learn_husky workspace
2. Install mocha as a dev dependency

    ```bash
        npm install --save-dev mocha
        # you should see it in package.json -> devDependencies 
    ```

3. Create a test folder

    ```bash
        mkdir test
        code test/test.js
    ```

4. You find a first test <https://mochajs.org/#getting-started>

    ```bash
        var assert = require('assert');
        describe('Array', function() {
        describe('#indexOf()', function() {
            it('should return -1 when the value is not present', function() {
            assert.equal([1, 2, 3].indexOf(4), -1);
              });
            });
        });
    ```

5. In package.json modify the scripts test in package.json [docs](https://mochajs.org/#the-test-directory)

    ```bash
        "scripts": {
            "test": "mocha"
        }
    ```

6. Run your first test

    ```Bash
    npm test
    ```

### Group Exercise

1. Make sure all in the team has a functional setup with husky and one mocha test
2. Investigate how hooks work in mocha <https://mochajs.org/#hooks>
   1. What is the order of execution?
   2. Write some more tests
   3. What happens if you put a describe nested within a describe?
   4. Learn to use only <https://mochajs.org/#exclusive-tests>
   5. Test to skip <https://mochajs.org/#inclusive-tests>
   6. Add a subfolder in the test folder, add another test in that subfolder.
      1. It will not run, why? read <https://mochajs.org/#the-test-directory>
      2. Change scripts test in package.json so the subfolder are included.

### Commit lint [Optional]

   1. Try the commitlint setup

       ```bash
       # Intall commitlint
       npm install -g @commitlint/cli @commitlint/config-conventional

       # Add default conf
       echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js

       # Add to husky
       npx husky add .husky/commit-msg 'npx --no-install commitlint --edit "$1"'
       ```

### Mocha tests

1. We will write a calculator using tests
2. Write a test that verifies add(1, 2) is 3
3. Run the test and be sure it fails "RED"
4. Write the code so the test passes "GREEN"
5. Make sure you are happy with the code "REFACTOR" and run the test again
6. Write a test that verifies add(0, 0) is 0
   1. "RED" -> "GREEN" -> "REFACTOR" as in step 3 - 5
7. Continue writing tests and implement code:
   1. add(-1, 0) is -1
   2. add(-1, -1) is -2
   3. add(-1, 1) is 0
8. Continue writing tests and implement code:
   1. multi(1, 1) is 1
   2. multi(1, 0) is 0
   3. multi(0, 1) is 0
   4. multi(2, 2) is 4
   5. multi(-2, 2) is -4
   6. multi(-2, -2) is 4
