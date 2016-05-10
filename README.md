# SpaceKit


## Install

```bash
$ npm install spacekit -g
```


## Usage

```plain
Usage: spacekit <name> [portMappings...]

Options:

  -h, --help     output usage information
  -V, --version  output the version number
```


## Examples

### Serve a local website

```bash
$ spacekit laptop 8080
```

This will map traffic from laptop.<username>.spacekit.io to the website/app you
have hosted on port 8080.


## Mapping ports

Port `443` is the default source port. So for brevity you can just supply the
destination port (ex: `8080`).

```bash
$ spacekit laptop 8080

# same as

$ spacekit laptop 443:8080
```

You can even map to other computers on your local network.

```bash
$ spacekit laptop 443:192.168.0.12:8080
```

You're able to map multiple ports on a single relay. When doing do you need to
be explicit. Port `443` and the port range `8000-8999` are valid source port
options.

```bash
$ spacekit laptop 443:8080 8100:8100
```


## Config file

Configuration is read from and written to `~/spacekit.json`.


## Logs

You can control the verbosity of logging via the `LOG_LEVEL` environment
variable. Options include `trace`, `debug`, `info`, `warn`, `error` and
`fatal`.


## License

Apache License, Version 2.0
