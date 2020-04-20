## List of workflows

### Sample workflows. For each workflow describe the following elements:
- Dependencies. Presence of a certain file, a previous workflow, a system state...
- Configuration. Which config-settings does the workflow use? Folderpaths...
- Inputs. Which input is required to start the workflow, if any. Does the workflow require additional input
- Output. What does the workflow output, if any.
- Tasks. List of tasks included in workflow.
- Trigger. Manual, triggered by change in context, triggered be schedule.
- Schedule. If scheduled, when and how often is the workflow initiated? 

### TOC
- [Import Smartarkivering](#Import-Smartarkivering)
- [Distribute Files](#Distribute-Files)
- [Generate Derivative Files](#Generate-Derivative-Files)
- [Validate Checksums](#Validate-Checksums)
- [Quarantine Files](#Quarantine-Files)
- [Run QA](#Run-Quality-Assurance)
- [Upload Binary Files](#Upload-Binary-Files)
- [Fetch Backup Files](#Fetch-Backup-Files)
- [Batch Update Records](#Batch-Update-Records)
- [Fetch Updates From DBC](#Fetch-Updates-From-DBC)
- [Deployment to bitmagasin](#Deployment-to-bitmagasin)

### Import Smartarkivering

### Distribute Files

### Generate Derivative Files

### Validate Checksums
Validate all files in a given storage-location (azure, HD's...)

### Quarantine Files

### Run quality assurance
**Dependencies:**
None

**Configuration:**
1. "backup_files_path". Used to fetch backupfile
2. "qa_files_path". Used to save any errorfiles

**Inputs:**
1. Most recent Backup-file ("{date}_backup_oas.csv" or "{date}_backup_entities.csv").

**Tasks:**
1. Parse backup-file into json
2. For each entry (record or entity), run each QA-task:
    1. if resticted by privacy, test that no binary files are referenced by a href.
    2. if creator equals "Ib Hansen", test that ophavsret equals "All rights reserved"
3. Optional. If QA fails, then add registration to errorlist
4. Optional. Save any errorlists to "qa_files_path"

**Outputs:**
1. Optional. One or more lists of registrations, that require updating.
2. Optional. If any errorlists, then it triggers workflow: "Import QA-lists to SAM"

**Trigger:**
Triggered by change in "backup_files_path" or manually

**Scheduling:**
Not scheduled

### Upload Binary Files

### Fetch Backup Files

### Batch Update Records

### Fetch Updates From DBC

### Deployment to bitmagasin

