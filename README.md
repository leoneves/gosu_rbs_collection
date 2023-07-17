# gosu_rbs_collection: A collection of RBS for Lib Gosu gem

[RBS](https://github.com/ruby/rbs) is a standard type signature syntax for Ruby programs.
This is a community-managed collection of RBS files for gems that ship without RBS.

## Loading RBS from the repository

To use it put the content of this rbs_collection.yml in your project

```yml
sources:
  - name: leoneves/gosu_rbs_collection
    remote: https://github.com/leoneves/gosu_rbs_collection.git
    revision: main
    repo_dir: gems

path: .gem_rbs_collection 
```

Run
```console
$ rbs collection install
```

If `rbs_collection.yaml` exists, the installed RBSs are loaded automatically.
You do not need any configuration for `rbs` and `steep` commands.
