<pre>
select SerialNumber00 from PC_BIOS_DATA inner join System_Data on PC_BIOS_DATA.MachineID = System_Data.MachineID where System_Data.Name0 = "<ComputerName>" 
</pre>