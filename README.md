
<h1 align="center">pathbuster
  <br>
</h1>

<h4 align="center">A path-normalization pentesting tool</h4>

<p align="center">
  <a href="/LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg"/></a>
  <a href="https://www.rust-lang.org/"><img src="https://camo.githubusercontent.com/2ed8a73e5c5d21391f6dfc3ed93f70470c1d4ccf32824d96f943420163df9963/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4c616e67756167652d527573742d3138313731373f636f6c6f723d726564"/></a>
  <a href="https://github.com/ethicalhackingplayground/pathmbuster/issues"><img src="https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat"></a>
  <a href="https://twitter.com/z0idsec"><img src="https://img.shields.io/twitter/follow/z0idsec.svg?logo=twitter"></a>
  <a href="https://discord.gg/MQWCem5b"><img src="https://img.shields.io/discord/862900124740616192.svg?logo=discord"></a>
  <br>
</p>

---

<p align="center">
  <a href="#todos">Todos</a> •
  <a href="#installation">Installation</a> •
  <a href="#usage">Usage</a> •
  <a href="#examples">Examples</a> •
  <a href="#contributing">Contributing</a> •
  <a href="#license">License</a> •
  <a href="https://discord.gg/MQWCem5b">Join Discord</a> 
</p>

---

### Todos

- [x] Implement **--filter-status** which will filter the status codes.
- [x] Implement **--filter-body-size** which will filter the response sizes.
- [x] Implement **--drop-after-fail** which will ignore requests with the same response code multiple times in a row.
---

## Installation

Install rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Install pathbuster

```bash
cargo install pathbuster
```


## Usage

```bash
pathbuster -h
```

This command will show the tool's help information and present a list of all the switches that are available.

```
USAGE:
    pathbuster [OPTIONS] --urls <urls> --payloads <payloads> --wordlist <wordlist>

OPTIONS:
    -c, --concurrency <concurrency>
            The amount of concurrent requests [default: 1000]

        --drop-after-fail <drop-after-fail>
            ignore requests with the same response code multiple times in a row [default: 302,301]

        --filter-body-size <filter-body-size>
            [default: 0]

        --filter-status <filter-status>
            [default: 403]

    -h, --help
            Print help information

        --match-status <match-status>
            [default: 400]

    -o, --out <out>
            The output file

        --payloads <payloads>
            the file containing the traversal payloads [default: ./payloads/traversals.txt]

    -r, --rate <rate>
            Maximum in-flight requests per second [default: 1000]

        --timeout <timeout>
            The delay between each request [default: 10]

    -u, --urls <urls>
            the url you would like to test

    -V, --version
            Print version information

    -w, --workers <workers>
            The amount of workers [default: 1]

        --wordlist <wordlist>
            the file containing the wordlist used for directory bruteforcing [default:
            ./wordlists/wordlist.txt]
```

## Flags

| Flag             | Description                                                                |
| ----------------- | ------------------------------------------------------------------ |
| --urls | the file containing the urls to test make sure it contains a path
| --payloads | file containing the payloads to test |
| --match-status |  status code used to match internal responses |
| --filter-body-size |  used to filter the response body like ffuf  |
| --filter-status |  used to filter the response status code like ffuf  |
| --drop-after-fail |  specify a status code to ignore if it reoccurs more than 5 times in a row  |
| --rate | used set the maximum in-flight requests per second |
| --workers | number of workers to process the jobs |
| --timeout | the delay between each request |
| --concurrency | number of threads to be used for processing |
| --wordlist | the wordlist used for directory bruteforcing |
| --out | save output to a file |
| --help | prints help information |
| --version | prints version information |

## Examples

Usage:

```rust
$ pathbuster --urls crawls.txt --payloads traversals.txt -o output.txt
```

[![asciicast](https://asciinema.org/a/UByv5LMcC5sXkFDHybjWEbF26.svg)](https://asciinema.org/a/UByv5LMcC5sXkFDHybjWEbF26)


## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.


## License

Pathbuster is distributed under [MIT License](https://github.com/ethicalhackingplayground/pathbuster/blob/main/LICENSE)