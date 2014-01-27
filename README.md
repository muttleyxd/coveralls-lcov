# Coveralls::Lcov

Upload coverage information generated by LCOV to coveralls.io.

coveralls-lcov supports travis-ci.org only.

## Installation

Add this line to your application's Gemfile:

    gem 'coveralls-lcov'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install coveralls-lcov

## Usage

In .travis.yml

```
install:
  - sudo apt-get install -y lcov
  - sudo gem install coveralls-lcov
before_script:
  - ./autogen.sh
  - ./configure --enable-coverage
script:
  - make check
after_success:
  - lcov --compat-libtool --directory . --capture --output-file coverage.info
  - coveralls-lcov coverage.info
```

or by hand

```
$ coveralls-lcov --repo-token "YOUR TOKEN" coverage.info
```

## Contributing

1. Fork it ( http://github.com/<my-github-username>/coveralls-lcov/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
