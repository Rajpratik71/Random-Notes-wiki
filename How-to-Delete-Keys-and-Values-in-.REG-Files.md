### To delete a whole key use the minus "-" sign before the key name, like in the following example:
```
Windows Registry Editor Version 5.00

[-HKEY_LOCAL_MACHINE\Software\ExampleKey]
```

### To delete values use the minus "-" sign after the "=" sign for the intended value:
```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\Software\ExampleKey]
"Value1"=-
"Value2"=-
```