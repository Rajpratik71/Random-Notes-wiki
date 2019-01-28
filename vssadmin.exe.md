View VSS Providers:
```
C:\WINDOWS\system32> vssadmin list providers
vssadmin 1.1 - Volume Shadow Copy Service administrative command-line tool
(C) Copyright 2001-2013 Microsoft Corp.

Provider name: 'Microsoft Software Shadow Copy provider 1.0'
   Provider type: System``
   Provider Id: {b5946137-7b9f-4925-af80-51abd60b20d5}
   Version: 1.0.0.7
```

View VSS Writers:
```
C:\WINDOWS\system32>vssadmin list writers
vssadmin 1.1 - Volume Shadow Copy Service administrative command-line tool
(C) Copyright 2001-2013 Microsoft Corp.

Writer name: 'VSS Metadata Store Writer'
   Writer Id: {75dfb225-e2e4-4d39-9ac9-ffaff65ddf06}
   Writer Instance Id: {088e7a7d-09a8-4cc6-a609-ad90e75ddc93}
   State: [1] Stable
   Last error: No error
```

Applies to: Windows 2003+ 