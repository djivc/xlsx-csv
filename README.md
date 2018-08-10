# XLSX-CSV

Basic XLSX to CSV converter.

## Usage
```
XLSX-CSV 0.2.1
Converts XLSX-files to CSV

USAGE:
    xlsx-csv [FLAGS] [OPTIONS]

FLAGS:
    -h, --help       Prints help information
    -V, --version    Prints version information
    -v               Show verbose debug output

OPTIONS:
    -i <input>         Sets the input file
    -o <output>        Output directory [default: .]
```
The script can either be started by providing the input (and optionally output)-files or
by providing a (set of) config-files. For use of config-files see below.


## Configuration
The script comes with a default template configuration. The config files must reside in the 
same folder as the script.

```
xlsx-csv.exe
config/
    default.toml
```

Each configuration file consists of three parameters. 
* `debug`: bool (as a single parameter)
* `source`: with the parameter `path`
* `archive`: with the parameter `path`

The configuration files are already catered to the individual environment, but can be changed, if necessary. 

In order to deploy the script to an environment, an environment variable has to be set directly on the server,
since the respective configuration file is being loaded conditionally. If not present already, create an
environment variable in the desired environment, `RUN_MODE` and assign the respective value 
(e.g. `integration` for config file `config/integration.toml`).