# pylogix

This project will allow you to easily read/write values from tags in Rockwell Automation Logix based PLC's over Ethernet I/P using Python.  PLC models inclued CompactLogix, ControlLogix and Micro8xx.  Python2 and Python3 are both supported.

## Getting Started

There are currently no dependencies so you can get going quickly without having to install any other prerequiste packages.

### Installing

You can clone the repo with the following:

```
git clone https://github.com/dmroeder/pylogix.git
cd pylogix
python setup.py install --user
```

### Verifying Installation

To verify the installation on Linux, open the terminal and use the following commands:

```
python
from pylogix import PLC
print(PLC().Version)
```

### Your First Script:

The cloned repository will come with many examples, I'll give one here.  We'll read one simple tag and print out the value.

```
from pylogix import PLC
with comm as PLC()
    comm.IPAddress = '192.168.1.9'
    value = comm.Read('MyTagName')
    print(value)
```

NOTE: If your PLC is in a slot other than zero (like can be done with ControLogix), then you can specify the slot with the following:

```
comm.ProcessorSlot = 2
```

NOTE: If you are working with a Micro8xx PLC, you must set the Micro800 flag since the path is different:

```
comm.Micro800 = True
```

### Other Features

Pylogix has features other than simply reading/writing.  You can see all of them in the examples, I'll also list them here

* Discover()
* GetPLCTime()
* SetPLCTime()
* GetTagList()
* GetModuleProperties(slot=0)

## Authors
* **Burt Peterson** - *Initial work*
* **Dustin Roeder** - *Maintainer* - [dmroeder](https://github.com/dmroeder)
* **Fernando B.** - *Contributor* - [kodaman2](https://github.com/kodaman2)

## License

This project is licensed under Apache 2.0 License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

* Archie of AdvancedHMI for all kinds pointers and suggestions.
* Thanks to all of the users that have tested and provided feedback.
