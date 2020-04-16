## List of tasks

Tasks are conceived of in the following way:

- A workflow consists of one or more tasks.
- Each task requires certain input (file, stdin or systemstate)
- Each task performs a single, well-defined operation
- Each task produces a certain output (file, stdout, systemstate)
- Each task can be chained in a unix-like pipe
- Each task is a generator
- Each task is conceived as a cli-call, but can in practice be performed by python-modules, cli-tools or GUIs

It is paramount to select the right levels of abstraction and a common interface for all tasks.


- [Extract Format Metadata](#Extract-Format-Metadata)
- [Detect Personal Information](#Detect-Personal-Information)
- [Copy File](#Copy-File)
- [Generate Derivative File](#Generate-Derivative-File)
- [Generate Checksum](#Generate-Checksum)
- [Validate Checksum](#Validate-Checksum)
- [Validate Against JSONschema](#Validate-Against-JSONschema)
- [Extract Text](#Extract-Text)
- [Assign Unique Identifier](#Assign-Unique-Identifiers)
- [Quarantine](#Quarantine-Files)
- [Scan for Virus](#Virus-Scan)
- [Identify Format](#Identify-Format)
- [Validate Format](#Validate-Format)
- [Upload Binary File](#Upload-Binary-File)
- [Fetch Backup File](#Fetch-Backup-File)
- [Update Record](#Update-Record)

### Extract Format Metadata
Extract embedded metadata from a given fileformat (images, video, sound)

### Redact Personal Information
Flag any Personal Information in text-files (cpr, address, phonenumber...)

### Copy File
Copy from one filepath to another. Include validation of the copied file.

### Generate Derivative File
Convert a given file to any number of formats, sizes and qualities

### Generate Checksum
Generate checksum for a file

### Validate Checksum
Validate checksum for a file

### Validate Against JSONschema
Validate a json-file against the relevant jsonschema (pydantic model)

### Extract Text
Extract text from any fileformat

### Assign Unique Identifier
Maybe not.

### Quarantine
Send a file/folder to quarantine-folder

### Scan for Virus
Scan a file for viruses

### Identify Format
Identify the format of a given file

### Validate Format
Validate a given format (pdf via veraPDF,...)

### Upload Binary File

### Fetch Backup File

### Update Record
