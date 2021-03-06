---
title: ft_test
---
```plaintext
 FT_TEST performs selected FieldTrip test scripts or reports on previous test
 results from the dashboard database.

 Use as
   ft_test run             ...
   ft_test moxunit_run     ...
   ft_test report          ...
   ft_test compare         ...

 ========= Running simple tests scripts =========

 To execute a test and submit the results to the dashboard database, you would do
   ft_test run
 to run all test functions, or
   ft_test run test_bug46
 to run a selected test.

 Test functions should not require any input arguments. Any output arguments will
 not be considered.

 Additional optional arguments are specified as key-value pairs and can include
   dependency       = string
   upload           = string, upload test results to the dashboard, can be 'yes' or 'no' (default = 'yes')
   dccnpath         = string, allow files to be read from the DCCN path, can be 'yes' or 'no' (default is automatic)
   maxmem           = number (in bytes) or string such as 10GB
   maxwalltime      = number (in seconds) or string such as HH:MM:SS
   sort             = string, can be 'alphabetical', 'walltime', 'mem' or 'random' (default = 'alphabetical')
   returnerror      = string, whether give an error upon detecting a failed script, can be 'immediate', 'final', 'no' (default = 'no')

 ========= Running MOxUnit tests =========

 To execute tests using MOxUNit, you would do
   ft_test moxunit_run

 This feature is still experimental, but should support the same
 options as ft_test run (see above), and in addition:
   xmloutput         = string, filename for JUnit-like XML file with test
                       results (used for shippable CI).
   exclude_if_prefix_equals_failed = string, if set to false (or 'no')
                       then tests are also run if their filename starts
                       with 'failed'. If set to true (or 'yes'), which is
                       the default, then filenames starting with 'failed'
                       are skipped.

 ========= Reporting on tests =========

 To print a table with the results on screen, you would do
   ft_test report
 to show all, or for a specific one
   ft_test report test_bug46

 Additional query arguments are specified as key-value pairs and can include
   matlabversion    = string, for example 2016b
   fieldtripversion = string
   branch           = string
   arch             = string, can be glnxa64, maci64. win32 or win64
   hostname         = string
   user             = string

 Optionally, you may capture the output to get the results as a Matlab table
 array, in which case they are not automatically displayed.
   rslt = ft_test('report', 'fieldtripversion', 'cef3396');

 ========= Comparing tests =========

 To print a table comparing different test results, you would do
   ft_test compare matlabversion     2015b    2016b
   ft_test compare fieldtripversion  ea3c2b9  314d186
   ft_test compare arch              glnxa64  win32

 Additional query arguments are specified as key-value pairs and can include
   matlabversion    = string, for example 2016b
   fieldtripversion = string
   branch           = string
   arch             = string, can be glnxa64, maci64. win32 or win64
   hostname         = string
   user             = string

 See also FT_VERSION
```
