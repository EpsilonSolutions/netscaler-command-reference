#ssl dhParam

The following operations can be performed on "ssl dhParam":


##create ssl dhParam

Generates a Diffie-Hellman (DH) key.


##Synopsys

create ssl dhParam &lt;dhFile> [&lt;bits>] [-gen ( 2 | 5 )]


##Arguments

<b>dhFile</b>
Name of and, optionally, path to the DH key file. /nsconfig/ssl/ is the default path.
Maximum value: 63

<b>bits</b>
Size, in bits, of the DH key being generated.
Minimum value: 512
Maximum value: 2048

<b>gen</b>
Random number required for generating the DH key. Required as part of the DH key generation algorithm.
Possible values: 2, 5
Default value: 2



##Example

1)	create ssl dhparam /nsconfig/ssl/dh1024.pem 1024 -gen 5

##Related Commands

<ul><li><a href="../../../-ssl-vs/-ssl-vs">set ssl vserver</a></li><li><a href="../../../w-ssl-vs/w-ssl-vs">show ssl vserver</a></li></ul>



