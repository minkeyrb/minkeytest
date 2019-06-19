# Minkeytest!

![minkey](https://i.imgur.com/boZFEMu.png)

## Minitest hates you!

Minitest [thinks you suck](https://github.com/seattlerb/minitest/blob/e6bc4485730403faff6966c1671cf5de72b2d233/lib/minitest/test.rb#L31).  Minitest wants to make it hard for you.  Minitest thinks it knows better than you.

Let's minkeypatch Minitest!

## Minkeytest is for you!

Minkeytest likes you.  Minkeytest wants to make it easy for you.  Minkeytest knows how to give you options you need.  Let's use Minkeytest!

    gem install minkeytest
    
```ruby
require 'minkeytest'

# Use all the minkeypatches!
Minkeytest.full_minkey!

# Use one of the smart minkeypatches!
Minkeytest.natural_order!
```

## Minkeytest is gentle!

Minkeypatches don't change much!  Minkeypatches only fix unfriendly decisions!

Minitest is capricious!

```ruby
module Minitest
  def self.__run reporter, options
    suites = Runnable.runnables.reject { |s| s.runnable_methods.empty? }.shuffle
    parallel, serial = suites.partition { |s| s.test_order == :parallel }
    serial.map { |suite| suite.run reporter, options } +
      parallel.map { |suite| suite.run reporter, options }
  end
end
```

Minkeytest is helpful!

```ruby
module Minitest
  def self.__run(reporter, options)
    suites = Runnable.runnables.reject { |s| s.runnable_methods.empty?}
    suites.map { |suite| suite.run(reporter, options) }
  end
end
```



