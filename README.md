[![Join the chat at https://gitter.im/rdfhdt](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/rdfhdt)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.580298.svg)](https://doi.org/10.5281/zenodo.580298)

# C++ implementation of the HDT compression format

Header Dictionary Triples (HDT) is a compression format for RDF data
that can also be queried for Triple Patterns.  **This repository is a fork or hdt-cpp with modifications in order to be built on Windows using Visual Studio 2017 using CMAKE**.

## Getting Started

### Prerequisites

In order to compile this library, you need to have the following
dependencies installed:

- [CMAKE](https://www.cmake.org)

- [[Serd v0.28+](https://github.com/drobilla/serd) see https://github.com/drobilla/serd for the installation instructions. or you can use my custom [CMakeLists.txt](https://gist.github.com/pebbie/bad2ed2f5d868de596b6b3f81ca35662) to build serd using cmake.


### Installation

To compile and install, run the following commands under the directory
`hdt-cpp`.  This will also compile and install some handy tools.

```
mkdir build
cd build
cmake -G "Visual Studio 15 2017 Win64" .. -DBUILD_TESTS=ON
cmake --build .
cmake --build . --target INSTALL
```

see also [original README](README.md.original)

## Using HDT

After compiling and installing, you can use the handy tools that are
located in `hdt-cpp/libhdt/tools`.  We show some common tasks that can
be performed with these tools.

### RDF-2-HDT: Creating an HDT

HDT files can only be created for standards-compliant RDF input files.
If your input file is not standards-compliant RDF, it is not possible
to create an HDT files out of it.

```
$ ./rdf2hdt data.nt data.hdt
```

### HDT-2-RDF: Exporting an HDT

You can export an HDT file to an RDF file in one of the supported
serialization formats (currently: N-Quads, N-Triples, TriG, and
Turtle).  The default serialization format for exporting is N-Triples.

```
$ ./hdt2rdf data.hdt data.nt
```

### Querying for Triple Patterns

You can issue Triple Pattern (TP) queries in the terminal by
specifying a subject, predicate, and/or object term.  The questions
mark (`?`) denotes an uninstantiated term.  For example, you can
retrieve _all_ the triples by querying for the TP `? ? ?`:

    $ ./hdtSearch data.hdt
    >> ? ? ?
    http://example.org/uri3 http://example.org/predicate3 http://example.org/uri4
    http://example.org/uri3 http://example.org/predicate3 http://example.org/uri5
    http://example.org/uri4 http://example.org/predicate4 http://example.org/uri5
    http://example.org/uri1 http://example.org/predicate1 "literal1"
    http://example.org/uri1 http://example.org/predicate1 "literalA"
    http://example.org/uri1 http://example.org/predicate1 "literalB"
    http://example.org/uri1 http://example.org/predicate1 "literalC"
    http://example.org/uri1 http://example.org/predicate2 http://example.org/uri3
    http://example.org/uri1 http://example.org/predicate2 http://example.org/uriA3
    http://example.org/uri2 http://example.org/predicate1 "literal1"
    9 results shown.
    
    >> http://example.org/uri3 ? ?
    http://example.org/uri3 http://example.org/predicate3 http://example.org/uri4
    http://example.org/uri3 http://example.org/predicate3 http://example.org/uri5
    2 results shown.
    
    >> exit

### Exporting the header

The header component of an HDT contains metadata describing the data
contained in the HDT, as well as the creation metadata about the HDT
itself.  The contents of the header can be exported to an N-Triples
file:

```
$ ./hdtInfo data.hdt > header.nt
```

### Replacing the Header

It can be useful to update the header information of an HDT.  This can
be done by generating a new HDT file (`new.hdt`) out of an existing
HDT file (`old.hdt`) and an N-Triples file (`new-header.nt`) that
contains the new header information:

```
$ ./replaceHeader old.hdt new.hdt new-header.nt
```

## Contributing

Contributions are welcome!  Please base your contributions and pull
requests (PRs) on the `develop` branch, and not on the `master`
branch.

## License

`hdt-cpp` is free software licensed as GNU Lesser General Public
License (GPL). See `libhdt/COPYRIGHT`.
