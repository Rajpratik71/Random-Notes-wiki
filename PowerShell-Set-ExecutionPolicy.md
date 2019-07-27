If the ExecutionPolicy is set to Restricted, which it is by default, you will receive the following error when trying to run a PowerShell script:
<pre>
 File C:\Script.ps1 cannot be loaded because the execution of scripts is disabled on this system. 
 Please see "get-help about_signing" for more details.
 At line:1 char:9
 + .\pi.ps1 <<<<
     + CategoryInfo          : NotSpecified: (:) [], PSSecurityException
     + FullyQualifiedErrorId : RuntimeException
</pre>

To enable PowerShell scripts you run you will have to set the ExecutionPolicy to '''RemoteSigned''' or '''Unrestricted'''.

Open a PowerShell window with Administrative privileges and run the following command:
<pre>
 Set-ExecutionPolicy RemoteSigned
</pre>

or
<pre>
 Set-ExecutionPolicy Unrestricted
</pre>

To verifiy your current Execution Policy run:
<pre>
 Get-ExecutionPolicy
</pre>
