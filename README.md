# RFC Conformance Test Suite

This repository contains tools and specs for defining conformance tests for RFC protocols, that can be used across various libraries and implementations of these RFCs for testing and coverage

## Conformance Spec
RFC conformance tests are defined in YAML using a generated schema from this repository. The spec is written in [Apple PKL](https://pkl-lang.org) and compiled to JSON Schema in YAML and JSON formats.

## Spec Runner 

> Status: Experimental

The spec runner is intended to take one of the specs in this repo and run a test runner for the specifications, reporting coverage, failed tests, and current performance (benchmarks) on actions, giving a full-fledged report usable for checking.

In the future, I'd love to have this tested with current implementations of current specs existing, including [curl]().

## Contributing

Contributions to this repo are very much welcome! We would love to have you contribute to this repo.

### Adding more RFC specs

You can contribute to adding more RFC specs, even if you do not have PKL installed. 

If you do have PKL installed, you can:
- Create a new branch on this repo, most likely following the convention `rfc/<number>`
- Create a new directory at `rfc/<number>/`

If you do not have PKL installed, you will need to run an action to process the new spec, either implemented in JSON or YAML, and this will generate the PKL files needed. It is recommended to use the PKL flow in order to benefit from multi-file configuration implementation, as well as PKLs type safety and constraint enforcement. 

- You can implement the spec using JSON or YAML for the given RFC in a new branch called `rfc/influx/<number>`
- Create a new directory at `rfc/influx/<number>/`
- Write the spec inside the directory as needed
- Create a PR for the change
- Automatically, the given PR will be closed and replaced with a new one containing the changes to PKL squashed with the changes you've made. 
