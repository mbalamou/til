# Ruby

## Installation

* [chruby](https://github.com/postmodern/chruby)
* [ruby-install](https://github.com/postmodern/ruby-install#readme)
* [shadowenv](https://github.com/Shopify/shadowenv)

## IDEs

## Rubymine

* [TIL/JetBrains IDEs](./jetbrains-ides.md)
* [Remote debugging](https://www.jetbrains.com/help/ruby/attaching-to-remote-process.html)
* [Spring](https://www.jetbrains.com/help/ruby/spring.html)

## Visual Studio Code

* [Debugging Ruby](https://dev.to/dnamsons/ruby-debugging-in-vscode-3bkj)
* [Shadowenv extension](https://github.com/Shopify/vscode-shadowenv)

## Testing

* [test-unit](https://test-unit.github.io/)
* [minitest](https://github.com/seattlerb/minitest)
* [Assertions](http://docs.seattlerb.org/minitest/Minitest/Assertions.html)
* [rspec](https://rspec.info/)
* [tutorial](https://dev.to/exampro/testunit-writing-test-code-in-ruby-part-1-of-3-44m2)

## Package managment / Dependencies

```
# Update one package
bundle lock --update=packwerk
```

## Tips and tricks

```
$ pry
> Foo.instance_method(:method_symbol).source.display
```
