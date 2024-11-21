**BIOS Settings**
SATA Mode -	AHCI
EHCI/XHCI Hand-off - Enabled
SVM -	Enabled
CSM -	Disabled
Secure Boot -	Disabled 
Serial Port -	Disabled
Parallel Port -	Disabled

Remove "-v" in bootargs to display the Apple loading bar instead of a terminal when starting the PC.

Modify Core Count patches to match your CPU's cores amount.
Find four algrey - Force cpuid_cores_per_package patches under Kernel -> Patch in your config.

Modify these patches for your CPU physical cores. Change first pair of 00 in Replace of these patches to Hex value from below table.

e. g. for Ryzen 7 1700 with 8 Cores three modified patches should look like:
B8 00 0000 0000 -> B8 08 0000 0000
BA 00 0000 0000 -> BA 08 0000 0000
BA 00 0000 0090 -> BA 08 0000 0090
BA 00 0000 00 -> BA 08 0000 00

Physical CPU cores	Hex value
4 Cores           	04
6 Cores	            06
8 Cores           	08
12 Cores          	0C
16 Cores	          10
24 Cores          	18
32 Cores          	20

tested in mac os Big Sur - Ventura
