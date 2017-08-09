---
title: Airflow UnicodeEncodeError and logging level
layout: default
comments: true
---

I was using Airflow and trying to log the Japanese characters from database, but I got UnicodeEncodeError instead.  
Airflow: v1.8.0  

<!--more-->

And when I figure out it is because the characters I try to disable log or set logging level, and see [someone else](https://stackoverflow.com/questions/42173554/apache-airflow-control-over-logging-disable-adjust-logging-level) also was trying to do so but the current version is not support to set logging level, at least in the condition of not altering the source code.  

Error log:
```
Exception in thread Thread-1:
Traceback (most recent call last):
  File "/usr/local/lib/python2.7/threading.py", line 801, in __bootstrap_inner
    self.run()
  File "/usr/local/lib/python2.7/threading.py", line 754, in run
    self.__target(*self.__args, **self.__kwargs)
  File "/usr/local/lib/python2.7/site-packages/airflow/task_runner/base_task_runner.py", line 95, in _read_task_logs
    self.logger.info('Subtask: {}'.format(line.rstrip('\n')))
UnicodeEncodeError: 'ascii' codec can't encode characters in position 76-80: ordinal not in range(128)
```

This is another problem is if I was not checking the err log, I will never know why my dags are all hang there, no more logs , not updating status and even cannot start any other dags any more. This means if one dags get error, entire airflow will hang.

