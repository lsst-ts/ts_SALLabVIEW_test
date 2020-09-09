# SAL LabVIEW Test Framework

This package is used to do the automatic test of service abstraction layer (SAL) LabVIEW vi and record the test results.

## Platform

- CentOS 7
- LabVIEW 2018 SP1 64-bit Professional Version

## Needed Package

- [ts_sal](https://github.com/lsst-ts/ts_sal)
- [ts_opensplice](https://github.com/lsst-ts/ts_opensplice) (Use OpenSpliceDDS V6.9)
- JKI VI Package Manager 2017 (vipm)
- Caraya Unit Test Framework (installed by vipm)

## Use of SAL

1. Increase the stack size (to 100 MB) for the SAL LabVIEW monitor to use:

```bash
ulimit -s 100000
```

2. Setup the SAL environment by following the description in [ts_sal](https://github.com/lsst-ts/ts_sal).

3. Assign the domain name of data distribution service (DDS). For example,

```bash
export LSST_DDS_DOMAIN=test
```

4. Output the debug message in SAL monitor by the tag of `LSST_{CSC}_LVDEBUG`. In this package, the `Test` commandable SAL component (CSC) is used. Do the following in the command line:

```bash
export LSST_Test_LVDEBUG=1
```

## Do the Unit Test

1. You can run the `testAll.vi` under the `tests/` directory in `SalLabVIEWTest.lvproj` to do the unit tests by using the Caraya unit test framework.

2. To do the unit tests and generate the JUnit xml report from the command line, do the following command. The generated report (`testReport.xml`) will be in the `log/` directory.

```bash
labview64 tests/testAllWithXmlReport.vi
```

## Shell Script

The available shell scripts are under the `shellScript/` directory.

1. **rmSalSharedMem.sh**: Remove the SAL shared memories. Usage: `rmSalSharedMem.sh CSC_names`.
