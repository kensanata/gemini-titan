# Gemini & Titan for Bash

[Gemini](https://gemini.circumlunar.space/) is a light-weight text
protocol, a spiritual successor to text-only network protocols like
[finger](https://en.wikipedia.org/wiki/Finger_protocol) and
[gopher](https://en.wikipedia.org/wiki/Gopher_%28protocol%29). It's
like an early predecessor to the web. It features a few improvements
over earlier text-only protocols without featuring all the
complexities of the web. Like the web, it offers both a protocol and a
markup format.

- the protocol can serve any MIME-types
- the markup comes with its own text/gemini format
- this format provides for line wrapping
- it uses UTF-8 by default
- it mandates TLS

[Titan](https://communitywiki.org/wiki/Titan) is a light-weight text
protocol, inspired by Gemini, to write text resources back to a server
that supports both Gemini and Titan. This is ideal if you want to run
a [Gemini Wiki](https://alexschroeder.ch/cgit/gemini-wiki/about/).

This project offers two [Bash](https://www.gnu.org/software/bash/)
functions to illustrate how this would work.

## Gemini and Titan

The code declares two bash functions called “gemini” and “titan” with
which to read and write Gemini sites.

Here's how to read `gemini://alexschroeder/Test`:

```
gemini gemini://alexschroeder.ch:1965/Test
```

The scheme and port are optional:

```
gemini alexschroeder.ch/Test
```

Here's how to edit “titan://alexschroeder.ch/raw/Test” (the exact URLs
to use depend on the site):

```
echo hello | titan titan://alexschroeder.ch:1965/raw/Test hello
```

Again, the scheme and port are optional:

```
date | titan alexschroeder.ch/raw/Test hello
```

You can also post a text file:

```
titan alexschroeder.ch/raw/Test hello test.txt
```

So there's your workflow:

```
gemini alexschroeder.ch/Test > test.txt
vim test.txt
titan alexschroeder.ch/raw/Test hello test.txt
```

To install, source this file from your ~/.bashrc file:

```
source ~/src/gemini-titan/gemini.sh
```

Contact: [Alex Schroeder](https://alexschroeder.ch/wiki/Contact)
