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
that supports both Gemini and Titan.

This project offers two [https://www.gnu.org/software/bash/ Bash]
functions to illustrate how this would work.

To a test page:

```
gemini gemini://alexschroeder.ch/Test
```

To write a test page:

```
echo "Gordon Cooper" | titan titan://alexschroeder.ch/raw/Test hello
```

To install the two functions, source this file from your `~/.bashrc`
file:

```
source ~/src/gemini-titan/gemini.sh
```

Contact: [Alex Schroeder](https://alexschroeder.ch/wiki/Contact)
