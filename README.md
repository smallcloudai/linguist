# Refact Fork of Linguist

The original library is at https://github.com/github/linguist

This library is used on GitHub.com to detect blob languages, ignore binary or vendored files.

It is used in Refact self hosting server to preprocess source code files, as a part of the fine tuning procedure.


## Installation

Linguist is written in Ruby. Ruby is a lightweight language that will not mess up our computer much. On Ubuntu:

```
sudo apt-get install -y build-essential cmake pkg-config ruby-full ruby-bundler
```

Installation:

```
git clone https://github.com/smallcloudai/linguist
cd linguist
bundle install
rake build_gem
```

Refact will look for the executable `smc-linguist` in PATH.


## Usage

It's designed for batch mode, it reads stdin and writes to stdout:

```
echo -e "/etc/timezone\n/etc/lsb-release" | smc-linguist
```


## Criticism

If you take Python file, change its extension to .cpp (C++) linguist will not recognize the file as still being Python.

In other words, it doesn't look into the text itself sufficiently. Maybe a better solution is needed.
