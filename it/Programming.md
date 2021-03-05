# Programming

## Glossary

cross-platform (multiple-platform)
- software that works on multiple computing platforms (e.g. Windows, Linux, macOS)

just-in-time compilation
- compile during execution
 
 shim
 - a library that transparently intercepts API calls
 - e.g. for supporting an old API

## Paradigms

### Imperative

- programmer instructions
- types
  - procedural
  - object-oriented

### Declarative

- declare desired result
- types
  - functional
  	- applying and composing functions
  	- functions: first-class citizens
  	- e.g.: Erlang, Haskell 
  - logic
  	- based on formal logic
  	- e.g.: Prolog
  - mathematical

## Compression

- archive file: composed of one or more files with metadata

### Zip

- archive + compression
- Store: no compression
- lossless data compression
- mostly uses DEFLATE (Huffmann...)
- up to 4GB files --> zip64 up to 16EB
- [zip4j](https://github.com/srikanth-lingala/zip4j)
- [Apache Common Compress](https://commons.apache.org/proper/commons-compress/examples.html)

### Gzip

- based on DEFLATE
- compressed file or archive
- usually faster than zip
- can save more disk space than zip
- can be combined with tar to create archive compressed files

### Tar

- uncompressed archive file
