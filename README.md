BPMN Model Interchange Test Suite
=================================

BPMN 2.0 Test Cases (Models, Diagrams, Serializations) created by the BPMN Model Interchange Working Group (BPMN MIWG) at the OMG.

For more information see: http://www.omgwiki.org/bpmn-miwg

Here is a list of all tools that participated in the tests:

[<img height="350" src="http://bpmn-miwg.github.io/bpmn-miwg-tools/bpmn-tools-tested-for-model-interchange-screenshot.png">](http://bpmn-miwg.github.io/bpmn-miwg-tools/)

<a rel="license" href="http://creativecommons.org/licenses/by/3.0/deed.en_CA"><img alt="Creative Commons Licence" style="border-width:0" src="http://i.creativecommons.org/l/by/3.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/3.0/deed.en_CA">Creative Commons Attribution 3.0 Unported License</a>.


**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [BPMN Model Interchange Test Suite](#bpmn-model-interchange-test-suite)
  - [How to test a BPMN tool using this test suite?](#how-to-test-a-bpmn-tool-using-this-test-suite)
		- [1. Download Test Cases](#1-download-test-cases)
		- [2. Test Import, Export and/or Roundtrip of BPMN Models.](#2-test-import-export-andor-roundtrip-of-bpmn-models)
		- [3. Submit Your Test Results to BPMN MIWG](#3-submit-your-test-results-to-bpmn-miwg)
	- [Detailed Descrition of Test Procedures](#detailed-descrition-of-test-procedures)
		- [1. BPMN MIWG Import Test Procedure](#1-bpmn-miwg-import-test-procedure)
		- [2. BPMN MIWG Export Test Procedure](#2-bpmn-miwg-export-test-procedure)
		- [3. BPMN MIWG Roundtrip Test Procedure (BPMN Import and Export combined)](#3-bpmn-miwg-roundtrip-test-procedure-bpmn-import-and-export-combined)
		- [4. BPMN Import and Export not supported](#4-bpmn-import-and-export-not-supported)
	- [Repository Structure](#repository-structure)


How to test a BPMN tool using this test suite?
----------------------------------------------

Everybody is welcome to test BPMN tools and submit results to the working group, not just tools vendors.
Here is how you do it:

### 1. Download Test Cases
First download the [latest version of the BPMN Model Interchange Test Suite](https://github.com/bpmn-miwg/bpmn-miwg-test-suite/archive/master.zip) and unpack it.
There is a directory called `Reference`, which contains the files needed for testing.
Next to that, there will be multiple folders with test results of other tools.

### 2. Test Import, Export and/or Roundtrip of BPMN Models.
There are [different test procedures](#detailed-descrition-of-test-procedures) that can be performed
with the provided reference models depending on the capabilities of the tool.
You will find explanations of these procedures [below](#detailed-descrition-of-test-procedures).

### 3. Submit Your Test Results to BPMN MIWG
Package all result files in a zip file and send it via email to [MIWG@trisotech.com](mailto:MIWG@trisotech.com). Please use the following template for your email:

```
Vendor: 
Tool name: 
Version: 
Website: 
Supports BPMN 2.0: 
Has BPMN XML import: 
Has BPMN XML export: 
License: 
Notes: 
```

Alternatively, you may also [fork the repository](https://github.com/bpmn-miwg/bpmn-miwg-test-suite/fork_select) on GitHub
and submit test results through a [pull request](https://github.com/bpmn-miwg/bpmn-miwg-test-suite/pull/new/master). If you do so, make sure to update the [JSON file with the list of tools](https://github.com/bpmn-miwg/bpmn-miwg-test-suite/blob/master/tools-tested-by-miwg.json).

Usually one day after your submission our [automated tools](https://github.com/bpmn-miwg/bpmn-miwg-tools)
should have generated a [report that shows findings in your submitted files](http://bpmn-miwg.github.io/bpmn-miwg-tools/):

[<img height="250" src="http://bpmn-miwg.github.io/bpmn-miwg-tools/bpmn-tools-tested-for-model-interchange-screenshot.png">](http://bpmn-miwg.github.io/bpmn-miwg-tools/)

Note: By submitting test results you agree that they will be published under a <a rel="license" href="http://creativecommons.org/licenses/by/3.0/deed.en_CA">Creative Commons Attribution 3.0 Unported License</a>.


Detailed Descrition of Test Procedures
--------------------------------------

<table>
  <tr>
    <th>Available Features</th>
    <th>Possible Tests</th>
  </tr>
  <tr>
    <td>import only</td>
    <td>import, cross</td>
  </tr>
  <tr>
    <td>export only</td>
    <td>export</td>
  </tr>
  <tr>
    <td>import & export</td>
    <td>import, export, roundtrip, cross</td>
  </tr>
</table>

### 1. BPMN MIWG Import Test Procedure
If the tool under test supports the import of BPMN XML files, you can test that feature using the following procedure:

1. **Import** the BPMN XML file (*.bpmn) provided with a [reference model](#1-download-test-cases) into the tool, e.g. `A.1.0.bpmn`.
1. **Save the graphical representation** of the model as imported to a file named `<test id>-import.<file type>`, e.g. `A.1.0-import.png`.
You can either do that through an export feature of the tool, e.g. a PNG, JPEG or PDF Export, or by taking a screenshot of the canvas.
1. **Compare** the result with the image provided with the reference model, e.g. `A.1.0.png`.
1. **Report any findings** by [creating new issues](https://github.com/bpmn-miwg/bpmn-miwg-test-suite/issues/new) on GitHub – one for each finding. Here is a template for your issue reports:

```
    Tool name:
    Tool version:
    Test case id:
    Test procedure: import
    Description:
```

Repeat these steps for all reference models and [submit your result files to BPMN MIWG](#3-submit-your-test-results-to-bpmn-miwg).

### 2. BPMN MIWG Export Test Procedure
If the tool under test supports the export of BPMN XML files, you can test that feature using the following procedure:

1. **Draw** the model as shown in the image provided with a [reference model](#1-download-test-cases) into the tool, e.g. `A.1.0.png`.
1. **Save the graphical representation** of the model as drawn to a file named `<test id>-export.<file type>`, e.g. `A.1.0-export.png`.
You can either do that through an export feature of the tool, e.g. a PNG, JPEG or PDF Export, or by taking a screenshot of the canvas.
1. **Export** the model into a BPMN XML file (*.bpmn) named `<test id>-export.bpmn`, e.g. `A.1.0-export.bpmn`.
1. **Compare** the result with the BPMN XML file (*.bpmn) provided with the reference model, e.g. `A.1.0.bpmn`.
1. **Report any findings** by [creating new issues](https://github.com/bpmn-miwg/bpmn-miwg-test-suite/issues/new) on GitHub – one for each finding. Here is a template for your issue reports:

```
    Tool name:
    Tool version:
    Test case id:
    Test procedure: export
    Description:
```

Repeat these steps for all reference models and [submit your test results to BPMN MIWG](#3-submit-your-test-results-to-bpmn-miwg).

### 3. BPMN MIWG Roundtrip Test Procedure (BPMN Import and Export combined)
If the tool under test supports the import and export of BPMN XML files, you can test a roundtrip using the following procedure:

1. **Import** the BPMN XML file (*.bpmn) provided with a [reference model](#1-download-test-cases) into the tool, e.g. `A.1.0.bpmn`.
1. If not already done during an import test, **save the graphical representation** of the model as it is imported to a file named `<test id>-import.<file type>`, e.g. `A.1.0-import.png`.
You can either do that through an export feature of the tool, e.g. a PNG, JPEG or PDF Export, or by taking a screenshot of the canvas.
1. **Export** the model into a BPMN XML file (*.bpmn) named `<test id>-roundtrip.bpmn`, e.g. `A.1.0-roundtrip.bpmn`.
1. **Compare** the result with the BPMN XML file (*.bpmn) provided with the reference model, e.g. `A.1.0.bpmn`.
1. **Report any findings** by [creating new issues](https://github.com/bpmn-miwg/bpmn-miwg-test-suite/issues/new) on GitHub – one for each finding. Here is a template for your issue reports:

```
    Tool name:
    Tool version:
    Test case id:
    Test procedure: roundtrip
    Description:
```

Repeat these steps for all reference models and [submit your test results to BPMN MIWG](#3-submit-your-test-results-to-bpmn-miwg).

### 4. Optional: BPMN MIWG Cross Test Procedure (BPMN Roundtrip with results of other tools)
If the tool under test supports at least the import of BPMN XML files, you may optionally do a cross test with the roundtrip and export test results submitted by other tools:

1. **Import** the BPMN XML files (*.bpmn) exported from other tools as their [test results](#1-download-test-cases) into the tool, e.g. `A.1.0-roundtrip.bpmn` or `A.1.0-export.bpmn` from the folder of the other tool, e.g. `camunda Modeler 2.4.0`.
1. **Save the graphical representation** of the model as imported to a file named `<name of imported file>-import.<file type>`, e.g. `A.1.0-roundtrip-import.png` or `A.1.0-export-import.png`.
You can either do that through an export feature of the tool, e.g. a PNG, JPEG or PDF Export, or by taking a screenshot of the canvas.
Store the result file in a folder with the name and version of the other tool that exported the file, e.g. `camunda Modeler 2.4.0`.
1. **Export** the model into a BPMN XML file (*.bpmn) named `<name of imported file>-roundtrip.bpmn`, e.g. `A.1.0-roundtrip-roundtrip.bpmn` or `A.1.0-export-roundtrip.bpmn`.
Store the result file in a folder with the name and version of the other tool that exported the file, e.g. `camunda Modeler 2.4.0`.
1. **Compare** the result with the BPMN XML file (*.bpmn) provided with the reference model, e.g. `A.1.0.bpmn`, and/or the imported file, e.g. `A.1.0-roundtrip.bpmn` or `A.1.0-export.bpmn`.
1. **Report any findings** by [creating new issues](https://github.com/bpmn-miwg/bpmn-miwg-test-suite/issues/new) on GitHub – one for each finding. Here is a template for your issue reports:

```
    Tool name:
    Tool version:
    Name of imported file:
    Tool name of imported file:
    Tool version of imported file:
    Test procedure: cross
    Description:
```

Repeat these steps for all roundtrip and export test results of all tools and [submit your test results to BPMN MIWG](#3-submit-your-test-results-to-bpmn-miwg).

### 5. BPMN Import and Export not supported
If the tool does neither support import nor export of BPMN XML files you can not perform the tests described above. However, if the tool supports other model interchange formats, we are still interested to record this information:

1. Create a [new issue on GitHub](https://github.com/bpmn-miwg/bpmn-miwg-test-suite/issues/new)  with a text like:

```
    Tool name:
    Tool version:
    Description:
        The BPMN XML format is not supported.
        Model Interchange is only possible in the `XPDL` format.

```


Repository Structure
--------------------

The top level is either a vendor or the submitted reference. 
The second level holds the individual test case files in the form `<identifier>-<test type>.filetype`.

The vendor who provided the reference model for a test case will be identified in the summarizing spreadsheet `BPMN MIWG Test Case Structure.xlsx`.

- README.md (this file)
- BPMN MIWG Test Case Structure.xlsx
- Reference <-- reference files for testing
  <ul>
    <li>A.1.0.png
  - A.1.0.bpmn <-- look in spreadsheet `BPMN MIWG Test Case Structure.xlsx` to find vendor who provided this reference
  - ...
  </ul>
- Business Process Incubator 4.?.? <-- test results
  <ul>
    <li>A.1.0-import.png
  - A.1.0-export.png
  - A.1.0-export.bpmn
  - A.1.0-roundtrip.bpmn
  - ...
  </ul>
- camunda Modeler 2.0.11 <-- test results
  <ul>
    <li>A.1.0-import.png
  - A.1.0-roundtrip.bpmn
  - ...
  </ul>
- MID Innovator 11.5.1.30223 <-- test results
  <ul>
    <li>A.1.0-import.png
  - A.1.0-export.bpmn
  - ...
  </ul>
