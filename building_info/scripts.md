# Scripts

The user will be able to perform the different options that pyQ is capable to do using four different scripts:

## pyqs - pyQsubmit
Script for submitting jobs. It has two modes: the script input and the cli. 

### Usage

When working with the script input mode, the job will be sent as a `bash` script, including a header containing 
the '#pyQ' string, followed by the key and its value. Each key has to be input in a new line.

When working with the cli mode, the keys will be input as flags and the command to execute will be input with the 's' flag.

A combined mode is also possible. In this mode, all keys are specified in the script (as well as the commands to execute)
but also one, some or all the keys are also specified as flags in the CLI. In this case, the value of the keys input as flags
is the one that will be used.

#### Example
Script input:
```bash
pyqs script.sh
```
CLI:
```bash
pyqs -j jobname -c 1 -g 1 -t 1-00:00 -cp False -s touch example.txt
```
Combined:
```bash
pyqs -j jobname -t 1-00:00 script.sh
```

## pyqk - pyQkill 
Script for killing sent or running jobs.

### Usage
```bash
pyqk jobid
```
or
```bash
pyqk [options]
```

### Options
- -a/all jobname*: kills all jobs sent by user which jobname starts with the input string
- -A/ALL: kills all jobs sent by the user

## pyqq - pyQqueues
Script for printing the information about the sent scripts

### Usage
```bash 
pyqi [options]
```

### Options
- -u/user username: prints the jobs sent by 'username'. The default (when executing without any flag) is the user username
- -a/all: prints all the jobs sent (by any user)
- -r/running: prints all jobs running (sent by any user)
- -c/clean: hides cancelled, failed and killed jobs from printing (for this execution and the following)
- -A/all_hobsc: prints all the jobs ever sent by the user

## pyqi - pyQinformation
Script for printing information about the computer unit such as available CPU cores, available GPU units and CPU and GPU current usage.

### Usage
```bash
pyqi [options]
```

### Options
- f/full: prints a full report with more data.
- j/jobid: prints information regarding only the facilities used by a certain job (identified by its jobid) such as the GPU usage.

