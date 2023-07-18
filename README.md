# gosu_rbs_collection: A collection of RBS for Lib Gosu gem

[RBS](https://github.com/ruby/rbs) is a standard type signature syntax for Ruby programs.
This is a community-managed collection of RBS files for gems that ship without RBS.

## Loading RBS from the repository

### First install rbs and steep
```console
$ bundle add steep
$ bundle add rbs
```

To use it put the content of this rbs_collection.yaml in your project

```yml
sources:
  - name: leoneves/gosu_rbs_collection
    remote: https://github.com/leoneves/gosu_rbs_collection.git
    revision: main
    repo_dir: gems

path: .gem_rbs_collection

gems:
  # Skip loading rbs gem's RBS.
  # It's unnecessary if you don't use rbs as a library.
  - name: rbs
    ignore: true
  - name: steep
    ignore: true
  - name: json
    ignore: true
```

Run
```console
$ bundle e rbs collection install
```

## Run Steep
Init steep
```console
$ bundle e steep init
```

change file: Steepfile
```ruby
target :game do
  signature 'sig' # directory with your signatures

  check 'game' # directory and subdirectories with your code
  check 'lib' # another directory and subdirectories with your code
  check 'init' # another directory and subdirectories with your code

  library 'logger', 'yaml', 'erb' # stdlibs if not auto recognized
end
```

Run
```console
bundle e steep check
```

If you have any syntax error in one file, this file will be ignore in steep check
