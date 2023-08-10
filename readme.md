# TinyTest

*Because there are no existing test frameworks for Ruby™*

## What?

This is just a toy project. Don't take it seriously.

## Installation (Option A)

I'm not pushing this to RubyGems.org because it's a toy personal project and it would be poor form to junk up RubyGems.

So, reference this Github repo directly from your `Gemfile` and do the usual `$ bundle install` dance.

```ruby
gem "tinytest", github: "booty/tinytest"
```

## Installation (Option B)

Alternatively, if you're not using Bundler [you can use the `specific_install` gem](https://github.com/rdp/specific_install) to install TinyTest straight from Github. Neat.

```
gem install specific_install
gem specific_install booty/tinytest
```

## Usage

Define some tests in `myfile.rb`:

```ruby
require "tinytest"

class DoSomeTests
  include TinyTest

  # Have multiple test per method. Sure, why not.
  def test_something
    assert_equal(
      "olleH",                # expected result
      "Hello".reverse,        # actual result
      "value set correctly"   # label for your test
    )

    assert(
      (42.to_s == "42"),      # a thing that should be true
      "conversion works"      # label for your test
    )
  end

  # Method names will be used as headers/separators
  # in the output
  def test_something_else
    assert(
      (1 == 2),               # a thing that should be true
      "this will fail"        # label for your test
    )
  end
end
```

Run: (if not using Bundler)

```bash
ruby myfile.rb
```

Run: (if using Bundler)

```bash
bundle exec ruby myfile.rb
```

Sample output:

```
----[ test_something ]----
  👍 value set correctly
  👍 conversion works

----[ test_something_else ]----
  🚫 this will fail

----[ RESULTS ]----
  💀 passed:2 failed:1
```

## Contributing

I mean, okay.
