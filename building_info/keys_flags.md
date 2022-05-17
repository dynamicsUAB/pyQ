# Keys and/or flags for sending jobs

There will be two different ways for sending jobs: via the CLI, so using flags, and via an script, using keys in the file.

## How to use infile keys

Keys can be specified inside the sent script following this syntaxis:

```bash
#pyQ -key_short content
#pyQ --key_long content
```
Being 'key' the desired key and 'content' the content for the specified key. Only one key has to be specified in each line.

## List of keys/flags

- j/jobname: Name of the job
- c/cores: number of required CPUs
- g/gpus: number of required GPUs
- t/timelimit: time limit for the job [in dd-hh:mm:ss format]
- cp/copy: copy generated files to submit folder [True/False]

A configuration file will be accessible for defining default parameters.
