# Version History

0.0.4

- Use the new docker image in **Jenkinsfile.labview** and remove the not-needed step.

0.0.3

- Update the use of debug message in **README.md**.
- Add the **testGetEventTask.vi** to test to get the SAL event by LabVIEW.
- Update the **Jenkinsfile.labview** to use the private docker image in CTIO nexus.
- Use the test data with the following packages:
  - ts_sal (commit: c4db06e)
  - ts_idl (commit: b378b92)
  - ts_opensplice (commit: 0801214)
  - ts_xml (commit: 0878d18)

0.0.2

- Add the **testConnect.vi** to test the connection and release of the shared memory.

0.0.1

- Add the **LibReader** to read the event and telemetry in SAL LabVIEW library.
- Add the **TestProcess** to execute/kill the SAL monitor.
- Add the **Jenkinsfile** to support the automatic test.
