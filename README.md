![plot](https://niklas-heer.github.io/speed-comparison/assets/latest/combined_results.png "Speed comparison of programming languages")

---

# Speed comparison of programming languages

This projects tries to compare the speed of different programming languages.
In this project we don't really care about getting a precise calculation of pi. We only want to see how fast are the programming languages doing. <br />
It uses an implementation of the [Leibniz formula for π](https://en.wikipedia.org/wiki/Leibniz_formula_for_%CF%80) to do the comparison. <br />
Here is a video which explains how it works: [Calculating π by hand](https://www.youtube.com/watch?v=HrRMnzANHHs)

You can find the results here: https://niklas-heer.github.io/speed-comparison/

## Disclaimer

I'm no expert in all these languages, so take my results with a grain of salt.<br>
Also the findings just show how good the languages can handle floating point operations, which is only one aspect of a programming language.

You are also welcome to contribute and help me fix my possible horrible code in some languages. :smile:

## Languages used in this comparison

- [C](https://en.wikipedia.org/wiki/C_(programming_language))
- [Clojure](https://en.wikipedia.org/wiki/Clojure)
- [C++](hhttps://en.wikipedia.org/wiki/C%2B%2B)
- [Crystal](https://en.wikipedia.org/wiki/Crystal_(programming_language))
- [Elixir](https://en.wikipedia.org/wiki/Elixir_(programming_language))
- [Go](https://en.wikipedia.org/wiki/Go_(programming_language))
- [Java](https://en.wikipedia.org/wiki/Java_(programming_language))
- [Julia](https://en.wikipedia.org/wiki/Julia_(programming_language))
- [Javascript](https://en.wikipedia.org/wiki/JavaScript) using [Node.js](https://en.wikipedia.org/wiki/Node.js)
- [Lua](https://en.wikipedia.org/wiki/Lua_(programming_language))
- [Nim](https://en.wikipedia.org/wiki/Nim_(programming_language))
- [PHP](https://en.wikipedia.org/wiki/PHP)
- [Python](https://en.wikipedia.org/wiki/Python_(programming_language))
- [R](https://en.wikipedia.org/wiki/R_(programming_language))
- [Ruby](https://en.wikipedia.org/wiki/Ruby_(programming_language))
- [Rust](https://en.wikipedia.org/wiki/Rust_(programming_language))
- [Swift](https://en.wikipedia.org/wiki/Swift_(programming_language))

## Run it yourself

Everything is run by a Docker container and a bash script which envokes the programs.

To measure the execution time a [python package](https://pypi.python.org/pypi/lauda/1.2.0) is used.

### Requirements
- `Docker`
- [earthly](https://earthly.dev/)

### Run everything
Earthly allows to run everything with a single command:
```bash
earthly --config earthly-config.yml +all
```
This will run all tasks to collect all measurements and then run the analysis.

### Collect data
To collect data for all languages run:
```bash
earthly --config earthly-config.yml +collect-data
```

To collect data for a single languages run:
```bash
earthly --config earthly-config.yml +<replace me with language name>
```

### Analyse results
To generate the combined CSV out of all results use this command:
```bash
earthly --config earthly-config.yml +analysis
```

## FAQ

> Why do you also count reading a file and printing the output?

Because I think this is a more realistic scenario to compare speeds.

> Are the compile times included in the measurements?

No they are not included, because when running the program in the real world this would also be done before.

## TODO
<!-- TODO: move to github tasks instead -->
- [x] Add C++
- [x] Add run pypy for Python
- [x] Produce graphic with results
- [x] Add Java
- [x] Add Swift
- [x] Add R
- [x] Add Elixir
- [ ] Add Smalltalk
- [ ] Add C#
- [ ] Add Perl
- [ ] Add Kotlin
- [ ] Add Haskell
- [ ] Add Lisp
- [ ] Add Ada
- [ ] Add COBOL

## Thanks

### Contributors
Thanks to all the lovely contributors:
- [0xB00B](https://github.com/0xB00B)
- [oscardssmith](https://github.com/oscardssmith)
- [DirkieDurky](https://github.com/DirkieDurky)
- [PatrickTheDev](PatrickTheDev)
- [giordano](giordano)
- [yinheli](yinheli)

_(Please feel free to add yourself to the list.)_

### Special thanks
#### Shravan-1908
The `scbench` tool uses the great application [bench](https://github.com/Shravan-1908/bench) from [Shravan-1908](https://github.com/Shravan-1908) as a basis. Thank you very much for creating this tool!

#### Thomas
This projects takes inspiration from [Thomas](https://www.thomaschristlieb.de) who did a similar comparison [on his blog](https://www.thomaschristlieb.de/performance-vergleich-zwischen-verschiedenen-programmiersprachen-und-systemen/).
