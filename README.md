# olescan

THIS IS A WORK IN PROGRESS - Check updates regularly!

olescan is a lightweight wrapper aggregating the functionality of several tools
to facilitate automated scanning of MS OLE2 and MS Office documents. The tool is
not designed to cover advanced maldoc analysis but is to assist Level 1 Support Teams
in performing basic code analysis before escalating to Level 2/3 Support Teams (i.e. InfoSec Professionals).

Its analysis capabilities include:
   1. Scanning of macro-enabled file-types and detection of macros, embedded flash content or
      file encryption (oleid)
   2. Automatic code extraction, VBA stomping detection, decoding of common obfuscation
      methods including Hex encoding, StrReverse, Base64, Dridex, VBA expressions, and
      identification of IOCs from decoded strings (olvevba)
   3. Scanning of both encoded and decoded strings against YARA rules(olevba + yara)
   4. Scanning and detection of malicious VBA Macros using generic heuristics to check for
      auto - execution, system / memory writes and / or file execution outside the VBA context (mraptor)

Usage: olescan [Options] \<filename>
   
Options:

      -h, --help         show this help message and exit

      -r, --recurse      find files recursively in subdirectories

      -i, --input        input a delimited text file in-place of <filename> for scanning automation

      -o, --output       output scanning results into a delimited text file (e.g. -o "C:\results.csv")

      -q, --quiet        simple analysis result of SUSPICIOUS or CLEAN


Example Usage: olescan -q -i -o "C:\Results.csv" "C:\DocumentList.csv"