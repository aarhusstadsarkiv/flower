# Elements of a workflow system
This applies to a workflow system running on local machines. If it is to run in the cloud, additional or more complex elements might be necessary.

In addition to these basic buildingblocks, elements like an adminUI, clustering-capabilities or advanced permission-controls might be nice to have.


## Deamon
We need to deamonize the watcher and the scheduler

**Thoughts:** The deamon might just be a simple wrapper around the watcher and the scheduler

**Requirements:**

**Questions:**

## Watcher
Watches for changes if existing files or new files, among other things. Triggers workflow-jobs

**Thoughts:**

**Requirements:**

**Questions:**

## Scheduler
Trigger workflow-jobs at specific times or intervals 

**Thoughts:**

**Requirements:**

**Questions:**

## Job-store
DB-backend or simple file-based system

**Thoughts:**

**Requirements:**

**Questions:**

## Taskmanager/jobrunner
Tool to orchestrate the individual tasks that make up a given workflow-job

**Thoughts:**

**Requirements:**

**Questions:**

## Tasks (functions, cli-tools...)
List of individual task or clitools that it makes sense to develop or use.

**Thoughts:**

**Requirements:**

**Questions:**

## Configuration
Configuration has multiple options when it comes to design...

**Thoughts:**
Use default-settings and user-settings

**Requirements:**

**Questions:**
