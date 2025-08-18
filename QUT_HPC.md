# QSUB
## To watch your own jobs in real-time using qstat
```bash
watch qstat
```

## To see the available resources in HPC
```bash
qstat -q
```
# QSUB-- ARRAY JOBS
## Status of array job --in detail
```bash
qstat -f <job_id>[].aqua
```
## Details of each job
```bash
qstat -f <job_id>[<specific_number>].aqua
```

## Status of array job ( just Running, Error, Qued)
```bash
qstat -t <job_id>[].aqua
```
## Requested resourses
```bash
qjobs -x <job_id>[].aqua
```
