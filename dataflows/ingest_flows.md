## Examples of data in-flows

Includes examples of the many ways that preservable data enters the archive. From the first entry-folder

### Template

Copy this template for each in-flow described:
- **Decription**
  > Describe the in-flow from start to where it enters SAM
- **Datastructure**
  > Describe the usual structure of the datapackage flowing in
- **Flow**
  > Describe the steps in the flow, until it enters the virtual drive (M:)
- **Sender**
  > Does the data usually come from a specific place/person?
- **Receiver**
  > Who usually receives the data?
- **Entry-folder**
  > Which shared drive folder is the payload usually placed in, when ?
- **Hybrid/digital/analog**
  > Is the payload usually binary, analog or hybrid?
- **Embedded Metadata**
  > Does the payload come with metadata?
- **Relation to SAM**
  > Does the flow connect to SAM in any way

## smartarkivering.dk

- **Description**
  > In-flow from our online portal smartarkivering.dk
- **Datastructure**
  > Single folder with list of binary files with associated xml-files containing the user inputted metadata for one or more of the binary files
- **Flow**
  1. User-uploaded binary files and their associated xml-metadata files are manually kopied via sftp into "_SMARTARKIVERING/Smartarkivering_20191218-163833" from the external webserver.
  2. Run "08_config_smartFormatToCsv" from workflow-folder to convert the xml-files to SAM-compliant output: a single csv-file with ALL metadata and one or more folders with binary files from each session.
  3. The csv-file is then normalized and enhanced with OpenRefine.
  4. From SAM, jobs are created and populated with the produced metadata.
- **Sender**
  > Any citizen-user of smartarkivering.dk
- **Receiver**
  > Claus Juhl Knudsen
- **Entry-folder**
  > /_SMARTARKIVERING/Smartarkivering_{timestamp for lastest upload-session}
- **Hybrid/digital/analog**
  > Payload is always digital
- **Embedded Metadata**
  > User-generated metadata is always delivered alongside the binary files.
