The following PowerShell script will diplay the DFS path and remote share information for the specified DFS share name.
<pre>
cd .\
dfsutil root export \\<your domain name>\<your Dfs share name> dfs.xml

$dfs= [xml](get-content dfs.xml) 

$hash = $null
$hash = @{}

foreach($obj in $dfs.Root.Link) { 
    $hash.Add("\\<your domain name>\<your Dfs share name>\"+$obj.name, $obj.target."#text")
} 

del dfs.xml

$hash | Sort-Object | Format-Table -AutoSize
</pre>
Applies to: Windows 2008 Distributed File System 