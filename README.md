# Let's minkeypatch Minitest!

![minkey](https://i.imgur.com/boZFEMu.png)

Minitest thinks you suck.  Let's minkeypatch Minitest!

## Run tests **AND suites** in order!

It's easy when you Minkeytest!


```ruby
module Minitest
  def self.__run(reporter, options)
    suites = Runnable.runnables.reject { |s| s.runnable_methods.empty?}
    suites.map { |suite| suite.run(reporter, options) }
  end
end
```

