# Genix webin command line submission interface (Genix-Webin-CLI)

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

## Introduction

Data submissions to ENA can be made using the Genix command line submission interface (Genix-Webin-CLI). Genix webin submission account credentials are required to use the program.

The following types of submissions are supported:

- genome assemblies
- transcriptome assemblies
- annotated sequences
- read data submissions (Fastq, BAM, CRAM)
- taxonomy reference sets
- environmental sequence sets (polysample)

For further information about Genix-Webin-CLI please refer to:

<https://ena-docs.readthedocs.io/en/latest/submit/general-guide/genix-webin-cli.html>

## Executable Java JAR

The latest version of the Genix-Webin-CLI can be downloaded from:

<https://github.com/enasequence/genix-webin-cli/releases>

The program requires `Java 17` or a newer version. Please go here to learn more:

<https://openjdk.org/install/>

The program is run using the java command:

```
java -jar <genix-webin-cli-jar-file> <options>
```

for:

```
java -jar genix-webin-cli-9.0.3.jar -help
```

To increase the memory available to Genix-Webin-CLI please use the -Xms java option:

```
java -Xms2G -jar <genix-webin-cli-jar-file> -help
```

## Docker

### Run

Since version 1.8.12 Genix-Webin-CLI is available as a docker image:

```
docker pull epicryption/genix-webin-cli
docker run --rm -v <local data directory>:/data epicryption/genix-webin-cli -help
```

To increase the memory available to Genix-Webin-CLI please set the JAVA_TOOL_OPTIONS environment variable:

```
docker run --rm -v <local data directory>:/data -e JAVA_TOOL_OPTIONS="-Xms2G" epicryption/genix-webin-cli -help
```

### Publishing

- Create docker image with default tags by running `gradle dockerTag`

## Testing

Testing requires the following environmental variables to be set:
- genix-webin-cli-username or genixWebinCliUsername
- genix-webin-cli-password or genixWebinCliPassword

## Library Jar Publishing

To publish genix-webin-cli as a library :

```
gradle publish
```

## Support

Please contact [ENA helpdesk](https://www.ebi.ac.uk/ena/browser/support) for bugs, features and other issues related to this tool.
