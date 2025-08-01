# Talend Job: LARGE_XML_Split_Into_small_xml2 -> LARGEXMLTosmallxml
Talend XML Splitter – ETL Job for Large XML Processing
This Talend job is designed to **split a large XML file** into smaller XML files based on your desired logic (e.g., node count, size, or structure). It consists of the following components:

## Job Flow
```
tPreJob → tFileTouch → tJava
```



### 1. tPreJob

- Initializes the job environment.
- Sets up required variables and directories (if needed).

### 2. tFileTouch

- Ensures a temporary or output file exists.
- Can be used to create an empty marker or destination file to be overwritten.

### 3. tJava

- Contains custom Java code that:
  - Reads the **Large XML file**.
  - Splits it into **smaller XML files** based on custom logic.
  - Writes each small XML file to the target directory.

---

## Folder Structure

```
/LARGE_XML_Split_Into_small_xml2/
│
├── /inputXML/         # Place the large input XML here
├── /outputPath/       # Small XML files will be written here
├── /TalendJob/        # Contains .item, .properties files etc.
├── /scripts/          # If any reusable custom code used
├── /screenshots/      # Folder for job screenshots
├── README.md
├── LICENSE            # MIT License file
```

---

## Prerequisites

- [Talend Open Studio](https://www.talend.com/products/talend-open-studio/) installed.
- Java JDK installed and properly configured.
- Place your **large XML file** inside the `inputXML` file path before running the job.
- outputPath or desired location as U:/Company/xyz/Datastage/src/xml/small/
- xmlFileName Note-> Only file Name without .xml (Example: "LARGEXMLFILE123")

---

## Running the Job

1. Open **Talend Open Studio**.
2. Import the project or job from this repository.
3. Configure the input/output file paths as needed.
4. Import Java modules
5. Run the job.

---

## Customization

- **Split Logic**: Modify the `tJava` component if:
  - You want to split based on tag depth, node count, or specific node names.
  - You want to change encoding or XML formatting.
- **File Naming**: Customize the naming pattern for small XML files (`file_1.xml`, `file_2.xml`, etc.) inside the `tJava` code.

---

## Example

**Input**:\
A single large XML file like:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<DSExp>
  <Job Identifier="DS123" DateModified="2020-22-23" TimeModified="03.17.19">
    <Record Identifier="ROOT" Type="JobDefn" Readonly="0">
      <Property Name="Name">DS123</Property>
      <Property Name="NextID">3</Property>
      ...
    </Record>
    ...
  </Job>
  <Job Identifier="DS456" DateModified="2020-22-23" TimeModified="07.23.23">
    <Record Identifier="ROOT" Type="JobDefn" Readonly="0">
      <Property Name="Name">DS456 </Property>
      <Property Name="NextID">3</Property>
      ...
    </Record>
    ...
  </Job>
  ...
</DSExp>
```

**Output**:\
Multiple files like:

```
outputPath/DS123.xml
outputPath/DS456.xml
...
```

Each containing a subset of `<Job>` nodes.



---

## Author

- **Tanmay Udaywal**
- [GitHub Profile](https://github.com/tanmayudaywal)

---

## License

This project is licensed under the [MIT License](LICENSE).\
You are free to use, modify, and distribute this project in accordance with the terms specified in the license.


