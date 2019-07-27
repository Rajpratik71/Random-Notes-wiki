Error: .NET Framework 2.0 is not installed. The installation cannot continue.

This error occurs even though you already have .Net 2.0 installed.

You will have to download SkipDotNetCheck.mst from [1] in order to get past this error.

You can use the following command-line syntax to install GP 10.0: 

 msiexec /i "D:\Bin\GreatPlains.msi" SQL_SERVER_NAME="SQL01" INSTALLDIR="C:\Program Files\Microsoft Dynamics\GP10" SELECTED_COUNTRY="United States" TRANSFORMS=:Inst02;C:\Downloads\skipdotnetcheck.mst INSTANCE_NAME="GP10" MSINEWINSTANCE=1 /qb+

Reference KB article 947539 https://mbs.microsoft.com/knowledgebase/KBDisplay.aspx?WTNTZSMNWUKNTMMYVLXUZLWUKKQPOVRVPQLLMRTZOXZMKWURYUMMLPMPXYSSUVNW&wa=wsignin1.0