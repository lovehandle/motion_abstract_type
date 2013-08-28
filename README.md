# motion_abstract_type

A RubyMotion port of [dkubb's](https://github.com/dkubb) [abstract_type](https://github.com/dkubb/abstract_type) library.

## Installation

Add this line to your application's Gemfile:

    gem 'motion_abstract_type'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install motion_abstract_type

## Usage

``` ruby
class Foo
  include AbstractType

  # Declare abstract instance method
  abstract_method :bar

  # Declare abstract singleton method
  abstract_singleton_method :baz
end

Foo.new  # raises NotImplementedError: Foo is an abstract type
Foo.baz  # raises NotImplementedError: Foo.baz is not implemented

# Subclassing to allow instantiation
class Baz < Foo; end

object = Baz.new
object.bar  # raises NotImplementedError: Baz#bar is not implemented
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
