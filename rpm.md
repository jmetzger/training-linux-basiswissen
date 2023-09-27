# RPM 

## Überprüfung installierte Dateien 

```
rpm -Va
# Attribute die dann angezeigt sind beschrieben in
man 8 rpm

 The format of the output is a string of 9 characters, a possible attribute marker:

       c %config configuration file.
       d %doc documentation file.
       g %ghost file (i.e. the file contents are not included in the package payload).
       l %license license file.
       r %readme readme file.

       from the package header, followed by the file name.  Each of the 9  characters  denotes
       the  result  of  a  comparison of attribute(s) of the file to the value of those attri‐
       bute(s) recorded in the database.  A single "." (period) means the test passed, while a
       single "?" (question mark) indicates the test could not be performed (e.g. file permis‐
       sions prevent reading). Otherwise,  the  (mnemonically  emBoldened)  character  denotes
       failure of the corresponding --verify test:

       S file Size differs
       M Mode differs (includes permissions and file type)
       5 digest (formerly MD5 sum) differs
       D Device major/minor number mismatch
       L readLink(2) path mismatch
       U User ownership differs
       G Group ownership differs
       T mTime differs
       P caPabilities differ
```
