# process replay

Process replay is a regression test designed to identify any changes in the output of a process. This test replays a segment through individual processes and compares the output to a known good replay. Each make is represented in the test with a segment.

If the test fails, make sure that you didn't unintentionally change anything. If there are intentional changes, the reference logs will be updated.

Use `test_processes.py` to run the test locally.

Currently the following processes are tested:

* controlsd
* radard
* plannerd
* calibrationd
* ubloxd

## Forks

openpilot forks can use this test with their own reference logs

To generate new logs:

`./update_refs.py --no-upload`

Then, check in the new logs using git-lfs. Make sure to also include the updated `ref_commit` file.
