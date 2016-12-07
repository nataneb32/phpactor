PhpActor
========

PHP introspection tool and code completion tool.

```php
./bin/phpactor complete 493 lib/Complete/ScopeFactory.php
```

Above it will try and find possible autocompletions at bye offet 493 of the
given file. You can also provide source via. stdin:

```php
cat ScopeFactory.php | ./bin/phpactor complete 493
```
Features
--------

- Uses [BetterReflection](https://github.com/roave/BetterReflection) to locate
  and introspect classes.
- No indexing required.
- Can infer property types from docblock annotations.
- Resolves variable types.
- Resolves chained object calls (providing return / parameter types are supplied).
- Simple omni complete VIM plugin (use it with [YouCompleteMe](https://github.com/Valloric/YouCompleteMe)

Limitations
-----------

- Only works for class scopes.
- Requires composer.

Why?
----

Because VIM hasn't got a good introspection / autocomplete tool.

VIM Integration
---------------

1. Copy (or better, symlink) `plugin/vim/autoload/phpactor.vim` to
`~/.vim/autoload/phpactor.vim`.
2. Set the omni-complete function to phpactor in your `.vimrc` and configure
   the path to `phpactor`: 

```
set omnifunc=phpactor#complete
let g:phpactor#phpactor_path="/home/daniel/www/dantleech/phpactor/bin/phpactor"
```

Other things
------------

- [Padawan](https://github.com/mkusher/padawan.vim): Looks very capable, but
  was pretty unstable last time I checked.
- [Atoms PHP integration](https://github.com/php-integrator/atom-base):
  Provides a PHP executable command to introspect code, but I really couldn't
  figure out how it worked.
