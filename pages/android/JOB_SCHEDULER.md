---
id: JOB_SCHEDULER
aliases: []
tags: []
index: 42
---

# JOB SCHEDULER

Element that allow multiple background tasks to be grouped together, in order to minimize battery drain, is based on 3 components

- **JobService** Service class where task is initiated
- **JobInfo** Builder pattern to set conditions for task
- **JobScheduler** Schedule and cancel tasks, launch service

the `JobService` class relies on 2 methods that are called on the main thread `onStartJob()` and `onStopJob()`

here an example using [async tasks](ASYNCHRONOUS_TECHNIQUES.md#ASYNC%20TASK):

```java
public class MyJobService extends JobService {
	private UpdateAppsAsyncTask updateTask = new UpdateAppsAsyncTask();

	@Override
	public boolean onStartJob(JobParameters params) {
		updateTask.execute(params);
		return true; // work has been offloaded
	}

	@Override
	public boolean onStopJob(JobParameters jobParameters) {
		return true;
	}
}
```

  There are also parameter that can be set to influence the scheduling of the job:

- minimum latency
- period
- network type
- if task requires the device to be plugged

[PREVIOUS](pages/android/ASYNCHRONOUS_TECHNIQUES.md) [NEXT](pages/android/ALARMS.md)
