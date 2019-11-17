# Intratime checker

![Status](https://img.shields.io/badge/Status-running-green.svg)
![Status](https://img.shields.io/badge/Language-python-yellow.svg)

<p align="center">
<img src="https://www.intratime.es/wp-content/uploads/2018/06/logo-intratime-control-horario.png">
</p>

Simple script for check-in/out using Intratime API


## How to use it

### Script mode

In this mode, the user makes the registration with a single order through some parameters.

> *Tip: This mode is recommended for automatic insertions, like a `cron job`.*

```
Usage: python intratime-checker.py [OPTIONS]

    -u, --user        [Required] Intratime user
    -p, --password    [Required] Intratime password
    -a, --action      [Required] Action: [in,out,pause,return]
    -d, --date        [Optional] Clock in/out date. E.g: 2019-06-16"
    -t, --time        [Optional] Clock in/out time. E.g: 09:00:00"
    -h, --help        Show this help.
```
**Example**

```
python intratime-checker.py -u user@gmail.com -p 81 -a out -d 2019-10-18 -t 17:34:22
```

### Interactive mode

In this mode the user stores his access credentials in a [configuration file](https://github.com/alberpilot/intratime-checker/blob/master/config.yaml), and can interactively enter the rest of the data after executing the script.

> *Tip: This mode is recommended if the user intends to enter the data manually.*

```
Usage: python intratime-checker.py
```

**Example**

```
python intratime-checker.py

Enter the date [YYYY-MM-DD] (default current date): 2019-10-29
Enter the time [HH:MM:SS] (default current time): 18:05:26
Enter the action [in, pause, return, out]: out
```