# Ruby

* [./Rails](./rails.md)
* [./Software Engineering](./software-engineering.md)

## Books

* [99 Bottles of OOP](https://sandimetz.com/99bottles)
* [Agile Web Development with Rails 7](https://pragprog.com/titles/rails7/agile-web-development-with-rails-7/)
* [Beginning Ruby 3 - From Beginner to Pro](https://link.springer.com/book/10.1007/978-1-4842-6324-2)
* [Metaprogramming Ruby 2](https://pragprog.com/titles/ppmetr2/metaprogramming-ruby-2/)
* [Practical Object-Oriented Design - An Agile Primer Using Ruby (POODR)](https://www.poodr.com/)
* [Programming Ruby 1.9 & 2.0](https://pragprog.com/titles/ruby4/programming-ruby-1-9-2-0-4th-edition/)
* [Refactoring Ruby Edition](https://martinfowler.com/books/refactoringRubyEd.html)

## Articles and blogs

* [The Practical Effects of the GVL on Scaling in Ruby](https://www.speedshop.co/2020/05/11/the-ruby-gvl-and-scaling.html)
* [To Thread or Not to Thread: An In-Depth Look at Ruby’s Execution Models](https://shopify.engineering/ruby-execution-models)

## Newsletters

* [Ruby Weekly](https://rubyweekly.com/) - A free, once–weekly e-mail round-up of Ruby news and articles

## Getting started

* [chruby](https://github.com/postmodern/chruby)
* [ruby-install](https://github.com/postmodern/ruby-install#readme)
* [shadowenv](https://github.com/Shopify/shadowenv)

### Install Ruby on macOS

* [Enable auto-switching](https://github.com/postmodern/chruby#auto-switching)

```
brew install ruby-install
brew install chruby
ruby-install ruby 2.7.2
chruby ruby-2.7.2
```

## IDEs

## Rubymine

* [TIL/JetBrains IDEs](./jetbrains-ides.md)
* [Remote debugging](https://www.jetbrains.com/help/ruby/attaching-to-remote-process.html)
* [Spring](https://www.jetbrains.com/help/ruby/spring.html)

## Visual Studio Code

* [Debugging Ruby](https://dev.to/dnamsons/ruby-debugging-in-vscode-3bkj)
* [Shadowenv extension](https://github.com/Shopify/vscode-shadowenv)

## Testing

* [Assertions](http://docs.seattlerb.org/minitest/Minitest/Assertions.html)
* [minitest](https://github.com/seattlerb/minitest)
* [rspec](https://rspec.info/)
* [test-unit](https://test-unit.github.io/)
* [tutorial](https://dev.to/exampro/testunit-writing-test-code-in-ruby-part-1-of-3-44m2)

## Gems and bundler - package managment and dependencies

```
# Update one package
bundle lock --update=packwerk

# Remove all unused gems in your bundler directory.
bundle clean --force
```

## Debugging

```
$ pry
> Foo.instance_method(:method_symbol).source.display
```
