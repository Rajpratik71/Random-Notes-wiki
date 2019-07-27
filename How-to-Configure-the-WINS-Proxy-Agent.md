The WINS proxy agent can only be configured on a WINS client computer. To enable the proxy agent change the value data of the following registry value:
<pre>
Key: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\NetBT\Parameters
Value: EnableProxy
String: 1
</pre>

Note: Only one WINS proxy should be configured per subnet.

Applies to: Windows NT 4.0 