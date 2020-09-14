# settings.json for vscode

可以通过各种设置配置 Visual Studio Code。VScode 编辑器的用户界面和功能行为都可以自定义。

VS Code 提供了两种不同的设置范围:

- **用户设置** - 全局应用于您打开的任何 VS Code 实例的设置。
- **工作区设置** - 存储在工作区中的设置，仅在打开工作区时适用

用户设置针对某一个具体的项目。而工作区设置针对每一个项目。用户设置的优先级大于工作区设置。

## EditorConfig

## Prettier

## ESLint

## StyleLint

## Vuter

## MarkdownLint

## Cspell

## recommend

工作区设置推荐如下

```json
{
  // window
  "window.zoomLevel": 0,

  // editor UI
  "editor.fontSize": 16,
  "editor.tabSize": 2,
  "editor.formatOnType": true,
  "editor.fontWeight": "500",
  "editor.formatOnSave": true,
  "editor.suggestSelection": "first",
  "editor.wordWrap": "on",
  // "editor.wrappingColumn": 120,
  "editor.codeActionsOnSave": {
    "source.fixAll": true,
    "source.fixAll.eslint": true,
    "source.fixAll.markdownlint": true,
    "source.fixAll.stylelint": true
  },
  // javascript
  "javascript.format.insertSpaceBeforeFunctionParenthesis": true,

  // files
  "files.autoSave": "afterDelay",

  // workbench
  "workbench.colorTheme": "Github",
  "workbench.sideBar.location": "left",
  "workbench.iconTheme": "material-icon-theme",
  "workbench.colorCustomizations": {
    "terminal.background": "#fff",
    "terminal.foreground": "#303030",
    "terminalCursor.background": "#303030",
    "terminalCursor.foreground": "#303030",
    "terminal.ansiBlack": "#F5F5F5",
    "terminal.ansiBlue": "#6A9FB5",
    "terminal.ansiBrightBlack": "#B0B0B0",
    "terminal.ansiBrightBlue": "#6A9FB5",
    "terminal.ansiBrightCyan": "#75B5AA",
    "terminal.ansiBrightGreen": "#90A959",
    "terminal.ansiBrightMagenta": "#AA759F",
    "terminal.ansiBrightRed": "#AC4142",
    "terminal.ansiBrightWhite": "#151515",
    "terminal.ansiBrightYellow": "#F4BF75",
    "terminal.ansiCyan": "#75B5AA",
    "terminal.ansiGreen": "#90A959",
    "terminal.ansiMagenta": "#AA759F",
    "terminal.ansiRed": "#AC4142",
    "terminal.ansiWhite": "#303030",
    "terminal.ansiYellow": "#F4BF75"
  },

  // Terminal
  "terminal.integrated.lineHeight": 1,
  "terminal.integrated.fontSize": 14,
  "terminal.integrated.fontFamily": "Meslo LG M for Powerline",
  "terminal.integrated.cursorBlinking": true,
  "terminal.integrated.rendererType": "dom",
  "terminal.integrated.cursorStyle": "line",

  //  ESLint
  "eslint.enable": true,
  // /"editor.defaultFormatter": "esbenp.prettier-vscode",
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "editor.formatOnSave": true
  },
  "eslint.validate": ["javascript", "javascriptreact", "vue"],
  "eslint.alwaysShowStatus": true,
  "eslint.options": {
    "env": {
      "browser": true,
      "es2020": true
    },
    "extends": [],
    "parserOptions": {
      "ecmaVersion": 12,
      "sourceType": "module"
    },
    "rules": {
      // best practice
      "accessor-pairs": "off",

      // enforces return statements in callbacks of array's methods
      // https://eslint.org/docs/rules/array-callback-return
      "array-callback-return": ["error", { "allowImplicit": true }],

      // treat var statements as if they were block scoped
      "block-scoped-var": "error",

      // specify the maximum cyclomatic complexity allowed in a program
      "complexity": ["off", 11],

      // enforce that class methods use "this"
      // https://eslint.org/docs/rules/class-methods-use-this
      "class-methods-use-this": [
        "error",
        {
          "exceptMethods": []
        }
      ],

      // require return statements to either always or never specify values
      "consistent-return": "error",

      // specify curly brace conventions for all control statements
      "curly": ["error", "multi-line"], // multiline

      // require default case in switch statements
      "default-case": ["error", { "commentPattern": "^no default$" }],

      // Enforce default clauses in switch statements to be last
      // https://eslint.org/docs/rules/default-case-last
      // TODO: enable, semver-minor, when eslint v7 is required (which is a major)
      "default-case-last": "off",

      // https://eslint.org/docs/rules/default-param-last
      // TODO: enable, semver-minor, when eslint v6.4 is required (which is a major)
      "default-param-last": "off",

      // encourages use of dot notation whenever possible
      "dot-notation": ["error", { "allowKeywords": true }],

      // enforces consistent newlines before or after dots
      // https://eslint.org/docs/rules/dot-location
      "dot-location": ["error", "property"],

      // require the use of === and !==
      // https://eslint.org/docs/rules/eqeqeq
      "eqeqeq": ["error", "always", { "null": "ignore" }],

      // Require grouped accessor pairs in object literals and classes
      // https://eslint.org/docs/rules/grouped-accessor-pairs
      // TODO: enable in next major, altho the guide forbids getters/setters anyways
      "grouped-accessor-pairs": "off",

      // make sure for-in loops have an if statement
      "guard-for-in": "error",

      // enforce a maximum number of classes per file
      // https://eslint.org/docs/rules/max-classes-per-file
      "max-classes-per-file": ["error", 1],

      // disallow the use of alert, confirm, and prompt
      "no-alert": "warn",

      // disallow use of arguments.caller or arguments.callee
      "no-caller": "error",

      // disallow lexical declarations in case/default clauses
      // https://eslint.org/docs/rules/no-case-declarations.html
      "no-case-declarations": "error",

      // Disallow returning value in constructor
      // https://eslint.org/docs/rules/no-constructor-return
      // TODO: enable, semver-major
      "no-constructor-return": "off",

      // disallow division operators explicitly at beginning of regular expression
      // https://eslint.org/docs/rules/no-div-regex
      "no-div-regex": "off",

      // disallow else after a return in an if
      // https://eslint.org/docs/rules/no-else-return
      "no-else-return": ["error", { "allowElseIf": false }],

      // disallow empty functions, except for standalone funcs/arrows
      // https://eslint.org/docs/rules/no-empty-function
      "no-empty-function": [
        "error",
        {
          "allow": ["arrowFunctions", "functions", "methods"]
        }
      ],

      // disallow empty destructuring patterns
      // https://eslint.org/docs/rules/no-empty-pattern
      "no-empty-pattern": "error",

      // disallow comparisons to null without a type-checking operator
      "no-eq-null": "off",

      // disallow use of eval()
      "no-eval": "error",

      // disallow adding to native types
      "no-extend-native": "error",

      // disallow unnecessary function binding
      "no-extra-bind": "error",

      // disallow Unnecessary Labels
      // https://eslint.org/docs/rules/no-extra-label
      "no-extra-label": "error",

      // disallow fallthrough of case statements
      "no-fallthrough": "error",

      // disallow the use of leading or trailing decimal points in numeric literals
      "no-floating-decimal": "error",

      // disallow reassignments of native objects or read-only globals
      // https://eslint.org/docs/rules/no-global-assign
      "no-global-assign": ["error", { "exceptions": [] }],
      // deprecated in favor of no-global-assign
      "no-native-reassign": "off",

      // disallow implicit type conversions
      // https://eslint.org/docs/rules/no-implicit-coercion
      "no-implicit-coercion": [
        "off",
        {
          "boolean": false,
          "number": true,
          "string": true,
          "allow": []
        }
      ],

      // disallow var and named functions in global scope
      // https://eslint.org/docs/rules/no-implicit-globals
      "no-implicit-globals": "off",

      // disallow use of eval()-like methods
      "no-implied-eval": "error",

      // disallow this keywords outside of classes or class-like objects
      "no-invalid-this": "off",

      // disallow usage of __iterator__ property
      "no-iterator": "error",

      // disallow use of labels for anything other then loops and switches
      "no-labels": ["error", { "allowLoop": false, "allowSwitch": false }],

      // disallow unnecessary nested blocks
      "no-lone-blocks": "error",

      // disallow creation of functions within loops
      "no-loop-func": "error",

      // disallow magic numbers
      // https://eslint.org/docs/rules/no-magic-numbers
      "no-magic-numbers": [
        "off",
        {
          "ignore": [],
          "ignoreArrayIndexes": true,
          "enforceConst": true,
          "detectObjects": false
        }
      ],

      // disallow use of multiple spaces
      "no-multi-spaces": [
        "error",
        {
          "ignoreEOLComments": false
        }
      ],

      // disallow use of multiline strings
      "no-multi-str": "error",

      // disallow use of new operator when not part of the assignment or comparison
      "no-new": "error",

      // disallow use of new operator for Function object
      "no-new-func": "error",

      // disallows creating new instances of String, Number, and Boolean
      "no-new-wrappers": "error",

      // disallow use of (old style) octal literals
      "no-octal": "error",

      // disallow use of octal escape sequences in string literals, such as
      // var foo = 'Copyright \251';
      "no-octal-escape": "error",

      // disallow reassignment of function parameters
      // disallow parameter object manipulation except for specific exclusions
      // rule: https://eslint.org/docs/rules/no-param-reassign.html
      "no-param-reassign": [
        "error",
        {
          "props": true,
          "ignorePropertyModificationsFor": [
            "acc", // for reduce accumulators
            "accumulator", // for reduce accumulators
            "e", // for e.returnvalue
            "ctx", // for Koa routing
            "context", // for Koa routing
            "req", // for Express requests
            "request", // for Express requests
            "res", // for Express responses
            "response", // for Express responses
            "$scope", // for Angular 1 scopes
            "staticContext" // for ReactRouter context
          ]
        }
      ],

      // disallow usage of __proto__ property
      "no-proto": "error",

      // disallow declaring the same variable more then once
      "no-redeclare": "error",

      // disallow certain object properties
      // https://eslint.org/docs/rules/no-restricted-properties
      "no-restricted-properties": [
        "error",
        {
          "object": "arguments",
          "property": "callee",
          "message": "arguments.callee is deprecated"
        },
        {
          "object": "global",
          "property": "isFinite",
          "message": "Please use Number.isFinite instead"
        },
        {
          "object": "self",
          "property": "isFinite",
          "message": "Please use Number.isFinite instead"
        },
        {
          "object": "window",
          "property": "isFinite",
          "message": "Please use Number.isFinite instead"
        },
        {
          "object": "global",
          "property": "isNaN",
          "message": "Please use Number.isNaN instead"
        },
        {
          "object": "self",
          "property": "isNaN",
          "message": "Please use Number.isNaN instead"
        },
        {
          "object": "window",
          "property": "isNaN",
          "message": "Please use Number.isNaN instead"
        },
        {
          "property": "__defineGetter__",
          "message": "Please use Object.defineProperty instead."
        },
        {
          "property": "__defineSetter__",
          "message": "Please use Object.defineProperty instead."
        },
        {
          "object": "Math",
          "property": "pow",
          "message": "Use the exponentiation operator (**) instead."
        }
      ],

      // disallow use of assignment in return statement
      "no-return-assign": ["error", "always"],

      // disallow redundant `return await`
      "no-return-await": "error",

      // disallow use of `javascript:` urls.
      "no-script-url": "error",

      // disallow self assignment
      // https://eslint.org/docs/rules/no-self-assign
      "no-self-assign": [
        "error",
        {
          "props": true
        }
      ],

      // disallow comparisons where both sides are exactly the same
      "no-self-compare": "error",

      // disallow use of comma operator
      "no-sequences": "error",

      // restrict what can be thrown as an exception
      "no-throw-literal": "error",

      // disallow unmodified conditions of loops
      // https://eslint.org/docs/rules/no-unmodified-loop-condition
      "no-unmodified-loop-condition": "off",

      // disallow usage of expressions in statement position
      "no-unused-expressions": [
        "error",
        {
          "allowShortCircuit": false,
          "allowTernary": false,
          "allowTaggedTemplates": false
        }
      ],

      // disallow unused labels
      // https://eslint.org/docs/rules/no-unused-labels
      "no-unused-labels": "error",

      // disallow unnecessary .call() and .apply()
      "no-useless-call": "off",

      // Disallow unnecessary catch clauses
      // https://eslint.org/docs/rules/no-useless-catch
      "no-useless-catch": "error",

      // disallow useless string concatenation
      // https://eslint.org/docs/rules/no-useless-concat
      "no-useless-concat": "error",

      // disallow unnecessary string escaping
      // https://eslint.org/docs/rules/no-useless-escape
      "no-useless-escape": "error",

      // disallow redundant return; keywords
      // https://eslint.org/docs/rules/no-useless-return
      "no-useless-return": "error",

      // disallow use of void operator
      // https://eslint.org/docs/rules/no-void
      "no-void": "error",

      // disallow usage of configurable warning terms in comments: e.g. todo
      "no-warning-comments": [
        "off",
        { "terms": ["todo", "fixme", "xxx"], "location": "start" }
      ],

      // disallow use of the with statement
      "no-with": "error",

      // require using Error objects as Promise rejection reasons
      // https://eslint.org/docs/rules/prefer-promise-reject-errors
      "prefer-promise-reject-errors": ["error", { "allowEmptyReject": true }],

      // Suggest using named capture group in regular expression
      // https://eslint.org/docs/rules/prefer-named-capture-group
      "prefer-named-capture-group": "off",

      // https://eslint.org/docs/rules/prefer-regex-literals
      // TODO; enable, semver-minor, once eslint v6.4 is required (which is a major)
      "prefer-regex-literals": "off",

      // require use of the second argument for parseInt()
      "radix": "error",

      // require `await` in `async function` (note: this is a horrible rule that should never be used)
      // https://eslint.org/docs/rules/require-await
      "require-await": "off",

      // Enforce the use of u flag on RegExp
      // https://eslint.org/docs/rules/require-unicode-regexp
      "require-unicode-regexp": "off",

      // requires to declare all vars on top of their containing scope
      "vars-on-top": "error",

      // require immediate function invocation to be wrapped in parentheses
      // https://eslint.org/docs/rules/wrap-iife.html
      "wrap-iife": ["error", "outside", { "functionPrototypeMethods": false }],

      // require or disallow Yoda conditions
      "yoda": "error",

      //errors
      "for-direction": "error",

      // Enforces that a return statement is present in property getters
      // https://eslint.org/docs/rules/getter-return
      "getter-return": ["error", { "allowImplicit": true }],

      // disallow using an async function as a Promise executor
      // https://eslint.org/docs/rules/no-async-promise-executor
      "no-async-promise-executor": "error",

      // Disallow await inside of loops
      // https://eslint.org/docs/rules/no-await-in-loop
      "no-await-in-loop": "error",

      // Disallow comparisons to negative zero
      // https://eslint.org/docs/rules/no-compare-neg-zero
      "no-compare-neg-zero": "error",

      // disallow assignment in conditional expressions
      "no-cond-assign": ["error", "always"],

      // disallow use of console
      "no-console": "warn",

      // disallow use of constant expressions in conditions
      "no-constant-condition": "warn",

      // disallow control characters in regular expressions
      "no-control-regex": "error",

      // disallow use of debugger
      "no-debugger": "error",

      // disallow duplicate arguments in functions
      "no-dupe-args": "error",

      // Disallow duplicate conditions in if-else-if chains
      // https://eslint.org/docs/rules/no-dupe-else-if
      // TODO: enable, semver-major
      "no-dupe-else-if": "off",

      // disallow duplicate keys when creating object literals
      "no-dupe-keys": "error",

      // disallow a duplicate case label.
      "no-duplicate-case": "error",

      // disallow empty statements
      "no-empty": "error",

      // disallow the use of empty character classes in regular expressions
      "no-empty-character-class": "error",

      // disallow assigning to the exception in a catch block
      "no-ex-assign": "error",

      // disallow double-negation boolean casts in a boolean context
      // https://eslint.org/docs/rules/no-extra-boolean-cast
      "no-extra-boolean-cast": "error",

      // disallow unnecessary parentheses
      // https://eslint.org/docs/rules/no-extra-parens
      "no-extra-parens": [
        "off",
        "all",
        {
          "conditionalAssign": true,
          "nestedBinaryExpressions": false,
          "returnAssign": false,
          "ignoreJSX": "all", // delegate to eslint-plugin-react
          "enforceForArrowConditionals": false
        }
      ],

      // disallow unnecessary semicolons
      "no-extra-semi": "error",

      // disallow overwriting functions written as function declarations
      "no-func-assign": "error",

      // https://eslint.org/docs/rules/no-import-assign
      // TODO: enable, semver-minor, once eslint v6.4 is required (which is a major)
      "no-import-assign": "off",

      // disallow function or variable declarations in nested blocks
      "no-inner-declarations": "error",

      // disallow invalid regular expression strings in the RegExp constructor
      "no-invalid-regexp": "error",

      // disallow irregular whitespace outside of strings and comments
      "no-irregular-whitespace": "error",

      // Disallow Number Literals That Lose Precision
      // https://eslint.org/docs/rules/no-loss-of-precision
      // TODO: enable, semver-minor, once eslint v7.1 is required (which is major)
      "no-loss-of-precision": "off",

      // Disallow characters which are made with multiple code points in character class syntax
      // https://eslint.org/docs/rules/no-misleading-character-class
      "no-misleading-character-class": "error",

      // disallow the use of object properties of the global object (Math and JSON) as functions
      "no-obj-calls": "error",

      // Disallow returning values from Promise executor functions
      // https://eslint.org/docs/rules/no-promise-executor-return
      // TODO: enable, semver-minor, once eslint v7.3 is required (which is major)
      "no-promise-executor-return": "off",

      // disallow use of Object.prototypes builtins directly
      // https://eslint.org/docs/rules/no-prototype-builtins
      "no-prototype-builtins": "error",

      // disallow multiple spaces in a regular expression literal
      "no-regex-spaces": "error",

      // Disallow returning values from setters
      // https://eslint.org/docs/rules/no-setter-return
      // TODO: enable, semver-major (altho the guide forbids getters/setters already)
      "no-setter-return": "off",

      // disallow sparse arrays
      "no-sparse-arrays": "error",

      // Disallow template literal placeholder syntax in regular strings
      // https://eslint.org/docs/rules/no-template-curly-in-string
      "no-template-curly-in-string": "error",

      // Avoid code that looks like two expressions but is actually one
      // https://eslint.org/docs/rules/no-unexpected-multiline
      "no-unexpected-multiline": "error",

      // disallow unreachable statements after a return, throw, continue, or break statement
      "no-unreachable": "error",

      // Disallow loops with a body that allows only one iteration
      // https://eslint.org/docs/rules/no-unreachable-loop
      // TODO: enable, semver-minor, once eslint v7.3 is required (which is major)
      "no-unreachable-loop": [
        "off",
        {
          "ignore": [] // WhileStatement, DoWhileStatement, ForStatement, ForInStatement, ForOfStatement
        }
      ],

      // disallow return/throw/break/continue inside finally blocks
      // https://eslint.org/docs/rules/no-unsafe-finally
      "no-unsafe-finally": "error",

      // disallow negating the left operand of relational operators
      // https://eslint.org/docs/rules/no-unsafe-negation
      "no-unsafe-negation": "error",

      // Disallow useless backreferences in regular expressions
      // https://eslint.org/docs/rules/no-useless-backreference
      // TODO: enable, semver-minor, once eslint v7 is required (which is major)
      "no-useless-backreference": "off",

      // disallow negation of the left operand of an in expression
      // deprecated in favor of no-unsafe-negation
      "no-negated-in-lhs": "off",

      // Disallow assignments that can lead to race conditions due to usage of await or yield
      // https://eslint.org/docs/rules/require-atomic-updates
      // note: not enabled because it is very buggy
      "require-atomic-updates": "off",

      // disallow comparisons with the value NaN
      "use-isnan": "error",

      // ensure JSDoc comments are valid
      // https://eslint.org/docs/rules/valid-jsdoc
      "valid-jsdoc": "off",

      // ensure that the results of typeof are compared against a valid string
      // https://eslint.org/docs/rules/valid-typeof
      "valid-typeof": ["error", { "requireStringLiterals": true }],

      // es6
      "arrow-body-style": [
        "error",
        "as-needed",
        {
          "requireReturnForObjectLiteral": false
        }
      ],
      "arrow-parens": 0,

      // require space before/after arrow function's arrow
      // https://eslint.org/docs/rules/arrow-spacing
      "arrow-spacing": ["error", { "before": true, "after": true }],

      // verify super() callings in constructors
      "constructor-super": "error",

      // enforce the spacing around the * in generator functions
      // https://eslint.org/docs/rules/generator-star-spacing
      "generator-star-spacing": ["error", { "before": false, "after": true }],

      // disallow modifying variables of class declarations
      // https://eslint.org/docs/rules/no-class-assign
      "no-class-assign": "error",

      // disallow arrow functions where they could be confused with comparisons
      // https://eslint.org/docs/rules/no-confusing-arrow
      "no-confusing-arrow": [
        "error",
        {
          "allowParens": true
        }
      ],

      // disallow modifying variables that are declared using const
      "no-const-assign": "error",

      // disallow duplicate class members
      // https://eslint.org/docs/rules/no-dupe-class-members
      "no-dupe-class-members": "error",

      // disallow importing from the same path more than once
      // https://eslint.org/docs/rules/no-duplicate-imports
      // replaced by https://github.com/benmosher/eslint-plugin-import/blob/master/docs/rules/no-duplicates.md
      "no-duplicate-imports": "off",

      // disallow symbol constructor
      // https://eslint.org/docs/rules/no-new-symbol
      "no-new-symbol": "error",

      // Disallow specified names in exports
      // https://eslint.org/docs/rules/no-restricted-exports
      // TODO enable, semver-minor, once eslint v7 is required (which is major)
      "no-restricted-exports": [
        "off",
        {
          "restrictedNamedExports": [
            "default", // use `export default` to provide a default export
            "then" // this will cause tons of confusion when your module is dynamically `import()`ed
          ]
        }
      ],

      // disallow specific imports
      // https://eslint.org/docs/rules/no-restricted-imports
      "no-restricted-imports": [
        "off",
        {
          "paths": [],
          "patterns": []
        }
      ],

      // disallow to use this/super before super() calling in constructors.
      // https://eslint.org/docs/rules/no-this-before-super
      "no-this-before-super": "error",

      // disallow useless computed property keys
      // https://eslint.org/docs/rules/no-useless-computed-key
      "no-useless-computed-key": "error",

      // disallow unnecessary constructor
      // https://eslint.org/docs/rules/no-useless-constructor
      "no-useless-constructor": "error",

      // disallow renaming import, export, and destructured assignments to the same name
      // https://eslint.org/docs/rules/no-useless-rename
      "no-useless-rename": [
        "error",
        {
          "ignoreDestructuring": false,
          "ignoreImport": false,
          "ignoreExport": false
        }
      ],

      // require let or const instead of var
      "no-var": "error",

      // require method and property shorthand syntax for object literals
      // https://eslint.org/docs/rules/object-shorthand
      "object-shorthand": [
        "error",
        "always",
        {
          "ignoreConstructors": false,
          "avoidQuotes": true
        }
      ],

      // suggest using arrow functions as callbacks
      "prefer-arrow-callback": [
        "error",
        {
          "allowNamedFunctions": false,
          "allowUnboundThis": true
        }
      ],

      // suggest using of const declaration for variables that are never modified after declared
      "prefer-const": [
        "error",
        {
          "destructuring": "any",
          "ignoreReadBeforeAssign": true
        }
      ],

      // Prefer destructuring from arrays and objects
      // https://eslint.org/docs/rules/prefer-destructuring
      "prefer-destructuring": [
        "error",
        {
          "VariableDeclarator": {
            "array": false,
            "object": true
          },
          "AssignmentExpression": {
            "array": true,
            "object": false
          }
        },
        {
          "enforceForRenamedProperties": false
        }
      ],

      // disallow parseInt() in favor of binary, octal, and hexadecimal literals
      // https://eslint.org/docs/rules/prefer-numeric-literals
      "prefer-numeric-literals": "error",

      // suggest using Reflect methods where applicable
      // https://eslint.org/docs/rules/prefer-reflect
      "prefer-reflect": "off",

      // use rest parameters instead of arguments
      // https://eslint.org/docs/rules/prefer-rest-params
      "prefer-rest-params": "error",

      // suggest using the spread operator instead of .apply()
      // https://eslint.org/docs/rules/prefer-spread
      "prefer-spread": "error",

      // suggest using template literals instead of string concatenation
      // https://eslint.org/docs/rules/prefer-template
      "prefer-template": "error",

      // disallow generator functions that do not have yield
      // https://eslint.org/docs/rules/require-yield
      "require-yield": "error",

      // enforce spacing between object rest-spread
      // https://eslint.org/docs/rules/rest-spread-spacing
      "rest-spread-spacing": ["error", "never"],

      // import sorting
      // https://eslint.org/docs/rules/sort-imports
      "sort-imports": [
        "off",
        {
          "ignoreCase": false,
          "ignoreDeclarationSort": false,
          "ignoreMemberSort": false,
          "memberSyntaxSortOrder": ["none", "all", "multiple", "single"]
        }
      ],

      // require a Symbol description
      // https://eslint.org/docs/rules/symbol-description
      "symbol-description": "error",

      // enforce usage of spacing in template strings
      // https://eslint.org/docs/rules/template-curly-spacing
      "template-curly-spacing": "error",

      // enforce spacing around the * in yield* expressions
      // https://eslint.org/docs/rules/yield-star-spacing
      "yield-star-spacing": ["error", "after"],

      // enforce or disallow variable initializations at definition
      "init-declarations": "off",

      // disallow the catch clause parameter name being the same as a variable in the outer scope
      "no-catch-shadow": "off",

      // disallow deletion of variables
      "no-delete-var": "error",

      // disallow labels that share a name with a variable
      // https://eslint.org/docs/rules/no-label-var
      "no-label-var": "error",

      // disallow declaration of variables already declared in the outer scope
      "no-shadow": "error",

      // disallow shadowing of names such as arguments
      "no-shadow-restricted-names": "error",

      // disallow use of undeclared variables unless mentioned in a /*global */ block
      "no-undef": 0,

      // disallow use of undefined when initializing variables
      "no-undef-init": "error",

      // disallow use of undefined variable
      // https://eslint.org/docs/rules/no-undefined
      // TODO: enable?
      "no-undefined": "off",

      // disallow declaration of variables that are not used in the code
      "no-unused-vars": [
        "error",
        { "vars": "all", "args": "after-used", "ignoreRestSiblings": true }
      ],

      // disallow use of variables before they are defined
      "no-use-before-define": [
        "error",
        { "functions": true, "classes": true, "variables": true }
      ]
    }
  },
  // prettier
  "prettier.enable": true,
  "prettier.requireConfig": false,
  "prettier.resolveGlobalModules": true,
  "prettier.tabWidth": 2,
  "prettier.semi": true,
  "prettier.singleQuote": true,
  "prettier.arrowParens": "avoid",
  "prettier.bracketSpacing": true,
  "prettier.trailingComma": "none",
  "prettier.jsxBracketSameLine": false,

  // cspell
  "cSpell.language": "en",
  "cSpell.enabled": true,
  "cSpell.enableFiletypes": [
    "css",
    "git-commit",
    "html",
    "python",
    "go",
    "javascript",
    "javascriptreact",
    "json",
    "jsx-tags",
    "markdown",
    "pug",
    "sass",
    "scss",
    "less",
    "text",
    "yaml",
    "vue"
  ],
  "cSpell.ignorePaths": [
    "node_modules", // this will ignore anything the node_modules directory
    "**/node_modules", // the same for this one
    "**/node_modules/**", // the same for this one
    "node_modules/**", // Doesn't currently work due to how the current working directory is determined.
    "vscode-extension", //
    ".git", // Ignore the .git directory
    "*.dll", // Ignore all .dll files.
    "**/*.dll" // Ignore all .dll files
  ],
  "cSpell.showStatus": true,

  // stylelint
  "stylelint.enable": true,
  "stylelint.autoFixOnSave": true,

  // Vetur
  "vetur.format.options.tabSize": 2,
  "vetur.format.enable": true,
  "todo-tree.tree.showScanModeButton": false,

  // jsx snippet
  "editor.snippetSuggestions": "top",

  // markdownlint
  "markdownlint.ignore": ["node_modules/**/*.md"],
  "markdownlint.config": {
    "default": true,
    "MD029": { "ol-prefix": "ordered" }
  },
  "leek-fund.funds": ["320007", "001549", "004746"],
  "leek-fund.iconType": "food1"
}
```
