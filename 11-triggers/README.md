# **TRIGGERS IN AZURE DATA FACTORY**
--------------------------------------------

In Azure Data Factory (ADF), a trigger is a component that determines when a pipeline execution should be 
start execution. Instead of manually running a pipeline, you can create a trigger and attach to automate the process.

ADF supports three main types of triggers:

1. **Schedule Trigger** 
- A schedule trigger runs a pipeline on a wall-clock schedule. This is the simplest and most common type of trigger.
- It allows for flexible scheduling, such as daily, weekly, or monthly. You can specify a start date and an end date.
- Ideal for routine, time-based tasks like a nightly data load or a daily report generation.

2. **Tumbling Window Trigger** 
- A tumbling window trigger runs on a periodic, non-overlapping, and fixed-size interval. It's designed for time-series 
  data and can manage dependencies on previous windows.
- The trigger fires for each time window (e.g., every 15 minutes, every hour). The WindowStart and WindowEnd variables 
  are automatically passed to the pipeline, which is useful for filtering data.
- A key feature is the ability to define dependencies. For example, a pipeline for a specific hourly window can be 
  configured to wait for the successful completion of the previous hour's run.
- Best for processing historical or incremental data, where you need to ensure that each time slice of data is 
  processed in a specific, non-overlapping order.

3. **Event-Based Trigger** 
- An event-based trigger initiates a pipeline in response to a specific event occurring in a storage account.
- The most common events are when a blob is created or a blob is deleted. This trigger subscribes to these events and
   kicks off a pipeline automatically.
- Perfect for event-driven architectures, such as when you need to process a file as soon as it's dropped into a 
  landing zone. This enables near-real-time data ingestion.

