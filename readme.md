# TinyTest

*Because there are no existing test frameworks for Ruby™*

## What?

This is just a toy project. Don't take it seriously.

## Usage

Reference this Github repo directly from your `Gemfile`.

I'm not pushing this to RubyGems.org because it's a toy personal project and it would be poor form to junk up RubyGems.

```ruby
gem "tinytest", github: "booty/tinytest"
```

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

Run:

```bash
ruby myfile.rb
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
