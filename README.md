[![Python Version](https://img.shields.io/badge/python-3.7-brightgreen.svg)](https://python.org)

# ALL ISSUES

## All ISSUES FACED:

### Error file: nimble/core/utils/helper.py
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

## Issue 1:
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

>       returnValidationConfigParser(OPTIONS_DICT["validationConfig"])

nimble/tests/conftest.py:63: 
 
nimble/core/configs/validation_config_parser.py:44: in __init__
    self.sqlite_adapter = SqliteAdapter(db_file=self.sqlite_file_path)
nimble/core/adapters/sqlite/sqlite_adapter.py:19: in __init__
    Helper.call_all(CustomFunctions(self.conn))
nimble/core/utils/helper.py:46: in call_all
    attribute(*args, **kwargs)
 

self = <nimble.core.adapters.sqlite.custom_functions.CustomFunctions object at 0x11b0a5210>

    def __native__(self):
        """
        Hook for the future.utils.native() function
        """
>       return object(self)
E       TypeError: object() takes no parameters
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


## Issue 2:
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
nimble/core/utils/report_utils.py:218: in dump_allure_env_file
    CsvUtils.dump_csv_as_key_value(dictionary, global_constants.DEFAULT_ALLURE_ENV_PATH, mode="a+", delimiter="=")
nimble/core/utils/csv_utils.py:108: in dump_csv_as_key_value
    writer.writerow([key, value])
../../Fabric_Convert/venv/lib/python3.7/site-packages/unicodecsv/py3.py:28: in writerow
    returnself.writer.writerow(row)
 

self = <unicodecsv.py3._UnicodeWriteWrapper object at 0x11997a748>
string = 'Project=platform\r\n'

    def write(self, string):
>       returnself.binary.write(string.encode(self.encoding, self.errors))
E       TypeError: write() argument must be str, not bytes
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


## Issue 3:
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
nimble/core/utils/report_utils.py:218: in dump_allure_env_file
    CsvUtils.dump_csv_as_key_value(dictionary, global_constants.DEFAULT_ALLURE_ENV_PATH, mode="a+", delimiter="=")
nimble/core/utils/csv_utils.py:108: in dump_csv_as_key_value
    writer.writerow([key, value])
../../Fabric_Convert/venv/lib/python3.7/site-packages/unicodecsv/py3.py:28: in writerow
    returnself.writer.writerow(row)

self = <unicodecsv.py3._UnicodeWriteWrapper object at 0x11997a748>
string = 'Project=platform\r\n'

    def write(self, string):
>       returnself.binary.write(string.encode(self.encoding, self.errors))
E       TypeError: write() argument must be str, not bytes




nimble/core/utils/fabric_utils.py:35: in run_command_on_remote
    returnoperations.run(command, timeout=command_timeout)

Next iterator:- https://link.springer.com/content/pdf/bbm%3A978-1-4302-2416-7%2F1.pdf

Pathlib2 available in 3.7 (still not downloaded)
Scandir available in 3.7 (still not downloaded)
Singledispatch available unto 3.4
Ipaddress  availableupto 3.6
enum34backportingupto 3.3 and not compatible with 3.6/3.7
Funsigs tested upto python3.5
Futures not compatible in python3
Contextlib2 tested in python3 no more information
Backport-abc=0.5 not installed in python3 and for running it in 3.7
 try:
     ABCs live in "collections.abc" in Python >= 3.3
fromcollections.abc import Coroutine, Generator
exceptImportError:
     fall back to import from "backports_abc"
frombackports_abc import Coroutine, Generator
Backport.function_lru_cache available for python>=2.6 but not installed for using it changes in python3
try:
fromfunctools import lru_cache
exceptImportError:
frombackports.functools_lru_cache import lru_cache

Avro not supported in python3:
Created virtual environment of python3 and install Avro using 
 pip install avro
Avro 1.9.0 installed
Run a python file containing import Avro
Error occurred:
Traceback (most recent call last):

  File "p.y", line 1, in <module>
    importavro
ModuleNotFoundError: No module named ‘avro'
But if we use Avro-python3 no error occurred.
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


## Issue 4: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
Python 2 is allowing string to be decoded again in string but Python 3 corrected this issue by showing ERROR: "'str' object has no attribute ‘decode’”. Solved above problem by opening file in bytes format and then decoding it into string format.
CHANGED IN FILE “CSV_UTILS.PY” AT LINE 37: with open(file path,’rb’) as f:
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


## Issue 5: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
"TypeError: '<' not supported between instances of 'collections.OrderedDict' and ‘collections.OrderedDict’”. Python 2 takes default value without key in sorted function whereas python 3 requires a key value to tell about what basis ordered Dict to be sorted therefore python3 giving above error.
But our code already giving sorted values so if we remove sorted function code runs in both python2 and python 3.
CHANGED IN FILE “CSV_UTILS.PY” AT LINE 33 AND 47: assert self.unicode_safe_list(list_of_dicts) == CsvUtils.parse_csv(self.file_)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


## Issue 6: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
In url.join it was overwriting /guavus/ with /tmp/.So, the solution found that if we write ./ before relative url it will concatenate both urls rather than overwriting /guavus/.

Before Changes at line 60 in file file_server_utils.py: module_path = re.sub(r'/+', "/", module_path)
After Changes at line 60 in file file_server_utils.py: module_path = re.sub(r'^/', "./", module_path)
From above two changes all test cases passed.
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


## Issue 7: 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
WARN ipc.Client: Exception encountered while connecting to the server : javax.security.sasl.SaslException: GSS initiate failed [Caused by GSSException: No valid credentials provided (Mechanism level: Failed to find any Kerberos tgt)]
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


# This is the transcript of all the contributions I performed in Guavus.

# Tasks Completed (12 - 06 -19):
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
1. Created virtual environment for Python2 and Python 3.
2. Understand about the uses of future library(http://python-future.org/automatic_conversion.html#step-0-setup) –
    1. Stage 1 : showing differences between python2 and python3 code without doing any changes in python code so, code is still in running stage in python2.
    2. Stage 2 : write the final changes in python file and make some manual changes as well.
3. Converted a little python 2 code to Python 3 code.
4. Knowledge about Fabric library:
    1. Automatically access Remote Desktop (server).
5. Removes manual requirements of again and again writing IP for accessing server system.
6. Run small piece of fabric code with python2 and python3. 
7. Fabric 1.x is compatible with Python2 only.
8. Find out about the need to migrate from fabric 1.x to 2.x.
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


# Task Completed (13-06-19):
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
9. Git clone this repo: st-automation.
10. Run sample_validation_hive in python 2 and fabric < 2.0 environment and then same running in python3 and fabric3 environment.
11.	Using fabric3 instead of fabric2 for python3 because fabric2 not includes below properties that are being used in fabric1.x:
    1. disableknown_hosts
    2. Abort_on_prompt
12.	Converting sample_validation_hive from python2 to python3 using future library.
13.	Command :futurize —stage1 st-automation/nimble
14.	Command:  futurize —stage2 -w st-automation/nimble
15.	Running code using all arguments and environment (python3 and fabric3).
16.	Error Detected:  File: sqlite_adapter  Line 19: Helper.call_all(CustomFunctions(self.conn)).
17.	If we comment above line then sample_validation_hive runs successfully. 
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


# Task Completed (17-06-19):
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
18.	Avro 1.9.0 not supported in python3 so tried version Avro-python3 but it alone doesn’t support libraries like : Avro.io. Avro and Avro-python3 used together succefullyrunned all libraries in python3 of Avro. Python2 doesn’t support avro-python3 (requires python>=3.4).
19.	In shell_utilsubprocess giving output in bytes therefore used encode=“utf-8” now, it gives output in string but in Python 2 there is no argument like encoding so the alternative found for this is "universal_newline”. 
Found on Documentation about Universal_Newline:" If encoding or errors are specified, or text is true, file objects for stdin, stdout and stderr are opened in text mode using the specified encoding and errors or the io.TextIOWrapper default. The universal_newlines argument is equivalent to text and is provided for backwards compatibility. By default, file objects are opened in binary mode.”

•	In actual_output_actions.py file giving Error: "TypeError: '>' not supported between instances of int and NoneType" for aggregation_level in line 92. Python3 doesn’t support comparison of None with int so, change the condition of if:
 Before Changes:
ifaggregation_level> 0 :
aggregate_column = "directory_name"
remove_grouped_column = True
if aggregate is True or aggregation_level> 0:
Error :TypeError: '>' not supported between instances of int and NoneType

 After Changes:
ifaggregation_level is not None and aggregation_level> 0 :
aggregate_column = "directory_name"
remove_grouped_column = True
if aggregate is True or (aggregation_level is not None and aggregation_level> 0 ):
Status:Successful
20. Only aggregation_level error is removed and code runs successfully (because aggregation_level is common file) but if there are more such commands where there is a comparison between None and int python3 will give error

TEST_VALIDATE_HIVE.PY WITH PYTHON 3, AVRO-PYTHON3, FABRIC3 RUNNED SUCCESSFULLY.
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


# REPORT (18-06-19):
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
    
  COMPONENT FOLDER FILES                                                 PYTHON 2                                                                PYTHON 3
1.	TEST_AMBARI_UTILS                                        TEST CASE FAILED : 0   TEST CASE PASSED: 7                           TEST CASE FAILED : 3   TEST CASE PASSED: 4
2.	TEST_ATLAS_UTILS                                           TEST CASE FAILED : 3   TEST CASE PASSED: 0                           TEST CASE FAILED : 3   TEST CASE PASSED: 0
3.	TEST_CDAP_UTILS                        TEST CASE FAILED : 19  IGNORED:5   TEST CASE PASSED: 0       TEST CASE FAILED : 19  IGNORED:5   TEST CASE PASSED: 0        
4.	TEST_COLLECTOR_UTILS                                 TEST CASE FAILED : 3   TEST CASE PASSED: 0                           TEST CASE FAILED : 3   TEST CASE PASSED: 0
5.	TEST_DOCKER_UTILS                                        TEST CASE FAILED : 9   TEST CASE PASSED: 2                           TEST CASE FAILED : 3   TEST CASE PASSED: 0
6.	TEST_ELASTICSEARCH_UTILS                          TEST CASE FAILED : 3   TEST CASE PASSED: 0                           TEST CASE FAILED : 3   TEST CASE PASSED: 0 
7.	TEST_HADOOP_UTILS                                        TEST CASE FAILED : 8   TEST CASE PASSED: 0                           TEST CASE FAILED : 8   TEST CASE PASSED: 0
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


# Task Completed (18-06-19):
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
TEST_VALIDATE_HBASE: NO UPDATE REQUIRED WORKED IN BOTH PYTHON 2 AND PYTHON 3.

UNIT TEST CASES FAILED OR PASSED IN PYTHON 2 and PYTHON 3
   
  UNIT TEST CASES									                                 PYTHON 2									                                                  PYTHON 3
1.	TEST_CUSTOM_FUNCTION                              TEST CASE FAILED : 4   TEST CASE PASSED: 2                           TEST CASE FAILED: 2.  TEST CASE PASSED: 2
2.	TEST_SQLITE_ADAPTER                                   TEST CASE FAILED : 0   TEST CASE PASSED: 4                           TEST CASE FAILED :1   TEST CASE PASSED: 3
3.	TEST_GUAVUS_RESPONSE                              TEST CASE FAILED : 0   TEST CASE PASSED: 1                           TEST CASE FAILED : 0  TEST CASE PASSED: 1
4.	TEST_FILTER                                                      TEST CASE FAILED : 0   TEST CASE PASSED: 7                           TEST CASE FAILED : 0   TEST CASE PASSED: 7
5.	TEST_JSON_PARSER                                        TEST CASE FAILED : 0   TEST CASE PASSED: 1                           TEST CASE FAILED : 0   TEST CASE PASSED: 1
6.	TEST_SINGLETON                                             TEST CASE FAILED : 0   TEST CASE PASSED: 1                           TEST CASE FAILED : 0   TEST CASE PASSED: 1
7.	TEST_BASE_TRANSFORMER                           TEST CASE FAILED : 0   TEST CASE PASSED: 1                           TEST CASE FAILED : 0   TEST CASE PASSED: 1
8.	TEST_COLLECTION_UTILS                               TEST CASE FAILED : 0   TEST CASE PASSED: 4                           TEST CASE FAILED : 8   TEST CASE PASSED: 0
9.	TEST_CSV_UTILS                                              TEST CASE FAILED : 0   TEST CASE PASSED: 11                         TEST CASE FAILED : 2   TEST CASE PASSED: 9
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


# Task Completed (28-06-19):
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
21.	In FILE_SERVER_UTILS there was an error showing no support for library urllib.parse in python 2 because in python3 this library is changed from URLPARSE (supported in python2) to URLLIB.PARSE. This change was made by future library. So, below changes made to solve above problem.
Before Changes:
fromurllib.parse import urlparse, urljoin
After Changes:
try:
fromurllib.parse import urlparse, urljoin
exceptImportError:
fromurlparse import urlparse, urljoin
•	There was one more error in above file that it was not getting response from correct url.
Expected Url: https://192.168.192.201/guavus/tmp/
Output Url: https://192.168.192.201/tmp/
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


# Task Completed (26-07-2019):
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
While searching for some securities issues in Python I came to know that python has some major security hole which are:
When we install any library from python (PyPi) a third-party library mostly our problem resolves but there is one big security issue that library can produce one of the major is it can make changes in your standard library or any other library used by you. In this way you opens the gate for hackers to hack your code or data.
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


# All my research on different Topics
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

Firstly, we should check whether that library is official or not and have a license.
For more information about the solution or checks to be made before installing any third-party library refer to this link.(https://hackernoon.com/10-common-security-gotchas-in-python-and-how-to-avoid-them-e19fbe265e03)
Then searched about if we have already coded then how to find these vulnerabilities.
Found: Bandit is an open source python library which solves some of our above issues (not all only standard ones).
For more information on bandit refer to this link.(https://pypi.org/project/bandit/)

Steps to run bandit library on our st-automation project:
  Step 1: '''pip install bandit (in virtual environment)'''
  Step 2: command for running bandit on project :- '''bandit -r st-automation -f html -o output.html''' 
Here: r -> indicates recursively
	 f ->project_folder
	 st-automation ->project_name
         Html -> type of output file you want
         Output.html -> output file (html)

Output File of Bandit:
Attached (in html format)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 


# References:
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 

## JIRA and Jenkins
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
https://www.youtube.com/watch?v=DktKQZVLhtE

## JIRA and Jenkins with Webhooks
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
https://www.youtube.com/watch?v=uhx3oDPOijo

## JIRA PLUGIN IN JENKINS
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
https://wiki.jenkins.io/display/JENKINS/JIRA+Plugin

_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ 
