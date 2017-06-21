#ssl

The following operations can be performed on "ssl":


##stat ssl

Displays SSL statistics.


##Synopsys

stat ssl [-detail] [-fullValues] [-ntimes &lt;positive_integer>] [-logFile &lt;input_filename>] [-clearstats ( basic | full )]


##Arguments

<b>detail</b>
Specifies detailed output (including more statistics). The output can be quite voluminous. Without this argument, the output will show only a summary.

<b>fullValues</b>
Specifies that numbers and strings should be displayed in their full form. Without this option, long strings are shortened and large numbers are abbreviated

<b>ntimes</b>
The number of times, in intervals of seven seconds, the statistics should be displayed.
Default value: 1
Minimum value: 0

<b>logFile</b>
The name of the log file to be used as input.

<b>clearstats</b>
Clear the statsistics / counters
Possible values: basic, full



##Outputs

<b># SSL cards UP (SSLCardUP)</b>
Number of SSL cards that are UP. If the number of cards UP is lower than a threshold, a failover is initiated.

<b>SSL crypto card status (SSLCardSt)</b>
Status of the SSL card(s). The value should be interpreted in binary form, with each set bit indicates a card as UP.

<b># SSL cards present (SSLCards)</b>
Number of SSL crypto cards present on the NetScaler appliance.

<b>SSL engine status (SSLEngSt)</b>
State of the SSL Engine (1=UP/0=DOWN). This state is decided based on SSL Feature/License status and minimum number of cards UP.

<b>SSL sessions  (SSLSe)</b>
Number of SSL sessions on the NetScaler appliance.

<b>SSL transactions (SSLTrn)</b>
Number of SSL transactions on the NetScaler appliance.

<b>SSLv2 transactions (SSL2Trn)</b>
Number of SSLv2 transactions on the NetScaler appliance.

<b>SSLv3 transactions (SSL3Trn)</b>
Total number of SSLv3 transactions on the NetScaler appliance.

<b>TLSv1 transactions (TLS1Trn)</b>
Number of TLSv1 transactions on the NetScaler appliance.

<b>TLSv1.1 transactions (TLS11Trn)</b>
Number of TLSv1.1 transactions on the NetScaler appliance.

<b>TLSv1.2 transactions (TLS12Trn)</b>
Number of TLSv1.2 transactions on the NetScaler appliance.

<b>SSLv2 sessions (SSL2Se)</b>
Number of SSLv2 sessions on the NetScaler appliance.

<b>SSLv3 sessions (SSL3Se)</b>
Number of SSLv3 sessions on the NetScaler appliance.

<b>TLSv1 sessions (TLS1Se)</b>
Number of TLSv1 sessions on the NetScaler appliance.

<b>TLSv1.1 sessions (TLS11Se)</b>
Number of TLSv1.1 sessions on the NetScaler appliance.

<b>TLSv1.2 sessions (TLS12Se)</b>
Number of TLSv1.2 sessions on the NetScaler appliance.

<b>new SSL sessions (NewSe)</b>
Number of new SSL sessions created on the NetScaler appliance.

<b>SSL session misses (SeMiss)</b>
Number of SSL session reuse misses on the NetScaler appliance.

<b>SSL session hits (SeHit)</b>
Number of SSL session reuse hits on the NetScaler appliance.

<b>SSL sessions (BSSLSe)</b>
Number of back-end SSL sessions on the NetScaler appliance.

<b>SSLv3 sessions (BSSL3Se)</b>
Number of back-end SSLv3 sessions on the NetScaler appliance.

<b>TLSv1 sessions (BTLS1Se)</b>
Number of back-end TLSv1 sessions on the NetScaler appliance.

<b>TLSv1.1 sessions (BTLS1Se)</b>
Number of back-end TLSv1.1 sessions on the NetScaler appliance.

<b>TLSv1.2 sessions (BTLS1Se)</b>
Number of back-end TLSv1.2 sessions on the NetScaler appliance.

<b>Session multiplex attempts (BSeMx)</b>
Number of back-end SSL session multiplex attempts on the NetScaler appliance.

<b>Session multiplex successes (BSeMxS)</b>
Number of back-end SSL session multiplex successes on the NetScaler appliance.

<b>Session multiplex failures (BSeMxF)</b>
Number of back-end SSL session multiplex failures on the NetScaler appliance.

<b>Bytes encrypted (Enc)</b>
Number of bytes encrypted on the NetScaler appliance.

<b>Bytes decrypted (Dec)</b>
Number of bytes decrypted on the NetScaler appliance.

<b>SSL session renegotiations (SSLRn)</b>
Number of SSL session renegotiations on the NetScaler appliance.

<b>SSLv3 session renegotiations (SSL3Rn)</b>
Number of session renegotiations done on SSLv3.

<b>TLSv1 session renegotiations (TLS1Rn)</b>
Number of SSL session renegotiations done on TLSv1.

<b>TLSv1.1 session renegotiations (TLS11Rn)</b>
Number of SSL session renegotiations done on TLSv1.1.

<b>TLSv1.2 session renegotiations (TLS12Rn)</b>
Number of SSL session renegotiations done on TLSv1.2.

<b>RSA 512-bit key exchanges (RSAKx5)</b>
Number of RSA 512-bit key exchanges on the NetScaler appliance.

<b>RSA 1024-bit key exchanges (RSAKx1)</b>
Number of RSA 1024-bit key exchanges on the NetScaler appliance.

<b>RSA 2048-bit key exchanges (RSAKx2)</b>
Number of RSA 2048-bit key exchanges on the NetScaler appliance.

<b>RSA 4096-bit key exchanges (RSAKx4)</b>
Number of RSA 4096-bit key exchanges on the NetScaler appliance.

<b>DH 512-bit key exchanges (DHKx5)</b>
Number of Diffie-Helman 512-bit key exchanges on the NetScaler appliance.

<b>DH 1024-bit key exchanges (DHKx1)</b>
Number of Diffie-Helman 1024-bit key exchanges on the NetScaler appliance.

<b>DH 2048-bit key exchanges (DHKx2)</b>
Number of Diffie-Helman 2048-bit key exchanges on the NetScaler appliance.

<b>ECDHE 521 curve key exchanges (ECDHEKx521)</b>
Number of 521 Elliptical Curve Diffie-Helman on the NetScaler appliance.

<b>ECDHE 384 curve key exchanges (ECDHEKx384)</b>
Number of 384 Elliptical Curve Diffie-Helman on the NetScaler appliance.

<b>ECDHE 256 curve key exchanges (ECDHEKx256)</b>
Number of 256 Elliptical Curve Diffie-Helman on the NetScaler appliance.

<b>ECDHE 224 curve key exchanges (ECDHEKx224)</b>
Number of 224 Elliptical Curve Diffie-Helman on the NetScaler appliance.

<b>RC4 40-bit encryptions (RC4En4)</b>
Number of RC4 40-bit cipher encryptions on the NetScaler appliance.

<b>RC4 56-bit encryptions (RC4En5)</b>
Number of RC4 56-bit cipher encryptions on the NetScaler appliance.

<b>RC4 64-bit encryptions (RC4En6)</b>
Number of RC4 64-bit cipher encryptions on the NetScaler appliance.

<b>RC4 128-bit encryptions (RC4En1)</b>
Number of RC4 128-bit cipher encryptions on the NetScaler appliance.

<b>DES 40-bit encryptions (DESEn4)</b>
Number of DES 40-bit cipher encryptions on the NetScaler appliance.

<b>DES 56-bit encryptions (DESEn5)</b>
Number of DES 56-bit cipher encryptions on the NetScaler appliance.

<b>3DES 168-bit encryptions (3DESEn1)</b>
Number of DES 168-bit cipher encryptions on the NetScaler appliance.

<b>AES 128-bit encryptions (AESEn1)</b>
Number of AES 128-bit cipher encryptions on the NetScaler appliance.

<b>AES 256-bit encryptions (AESEn2)</b>
Number of AES 256-bit cipher encryptions on the NetScaler appliance.

<b>RC2 40-bit encryptions (RC2En4)</b>
Number of RC2 40-bit cipher encryptions on the NetScaler appliance.

<b>RC2 56-bit encryptions (RC2En5)</b>
Number of RC2 56-bit cipher encryptions on the NetScaler appliance.

<b>RC2 128-bit encryptions (RC2En1)</b>
Number of RC2 128-bit cipher encryptions on the NetScaler appliance.

<b>AES-GCM 128-bit encryptions (AESGCMEn1)</b>
Number of AEC-GCM 128-bit cipher encryptions on the NetScaler appliance.

<b>AES-GCM 256-bit encryptions (AESGCMEn2)</b>
Number of AEC-GCM 256-bit cipher encryptions on the NetScaler appliance.

<b>Null cipher encryptions (NullEn)</b>
Number of Null cipher encryptions on the NetScaler appliance.

<b>MD5 hashes (MD5Hsh)</b>
Number of MD5 hashes on the NetScaler appliance.

<b>SHA hashes (SHAHsh)</b>
Number of SHA hashes on the NetScaler appliance.

<b>SSLv2 SSL handshakes (SSL2Hs)</b>
Number of handshakes on SSLv2 on the NetScaler appliance.

<b>SSLv3 SSL handshakes (SSL3Hs)</b>
Number of handshakes on SSLv3 on the NetScaler appliance.

<b>TLSv1 SSL handshakes (TLS1Hs)</b>
Number of SSL handshakes on TLSv1 on the NetScaler appliance.

<b>TLSv1.1 SSL handshakes (TLS11Hs)</b>
Number of SSL handshakes on TLSv1.1 on the NetScaler appliance.

<b>TLSv1.2 SSL handshakes (TLS12Hs)</b>
Number of SSL handshakes on TLSv1.2 on the NetScaler appliance.

<b>SSLv2 client authentications (SSL2CAt)</b>
Number of client authentications done on SSLv2.

<b>SSLv3 client authentications (SSL3CAt)</b>
Number of client authentications done on SSLv3.

<b>TLSv1 client authentications (TLS1CAt)</b>
Number of client authentications done on TLSv1.

<b>TLSv1.1 client authentications (TLS11CAt)</b>
Number of client authentications done on TLSv1.1.

<b>TLSv1.2 client authentications (TLS12CAt)</b>
Number of client authentications done on TLSv1.2.

<b>RSA authentications (RSAAt)</b>
Number of RSA authentications on the NetScaler appliance.

<b>DH authentications (DHAt)</b>
Number of Diffie-Helman authentications on the NetScaler appliance.

<b>DSS (DSA) authentications (DSSAt)</b>
Total number of times DSS authorization is used on the NetScaler appliance.

<b>Null authentications (NullAt)</b>
Number of Null authentications on the NetScaler appliance.

<b>SSL session renegotiations (BSSLRn)</b>
Number of back-end SSL session renegotiations on the NetScaler appliance.

<b>SSLv3 session renegotiations (BSSL3Rn)</b>
Number of back-end SSLv3 session renegotiations on the NetScaler appliance.

<b>TLSv1 session renegotiations (BTLS1Rn)</b>
Number of back-end TLSv1 session renegotiations on the NetScaler appliance.

<b>TLSv1.1 back-end session renegotiations (BTLS1aRn)</b>
Number of back-end TLSv1.1 session renegotiations on the NetScaler appliance.

<b>TLSv1.2 back-end session renegotiations (BTLS12Rn)</b>
Number of back-end TLSv1.2 session renegotiations on the NetScaler appliance.

<b>RSA 512-bit key exchanges (BRSAKx5)</b>
Number of back-end RSA 512-bit key exchanges on the NetScaler appliance.

<b>RSA 1024-bit key exchanges (BRSAKx1)</b>
Number of back-end RSA 1024-bit key exchanges on the NetScaler appliance.

<b>RSA 2048-bit key exchanges (BRSAKx2)</b>
Number of back-end RSA 2048-bit key exchanges on the NetScaler appliance.

<b>DH 512-bit key exchanges (BDHKx5)</b>
Number of back-end DH 512-bit key exchanges on the NetScaler appliance.

<b>DH 1024-bit key exchanges (BDHKx1)</b>
Number of back-end DH 1024-bit key exchanges on the NetScaler appliance.

<b>DH 2048-bit key exchanges (BDHKx2)</b>
Number of back-end DH 2048-bit key exchanges on the NetScaler appliance.

<b>ECDHE 521 curve key exchanges (BECDHECx1)</b>
Number of back-end ECDHE 521 curve Key exchanges  on the NetScaler appliance.

<b>ECDHE 384 curve key exchanges (BECDHECx2)</b>
Number of back-end ECDHE 384 curve Key exchanges  on the NetScaler appliance.

<b>ECDHE 256 curve key exchanges (BECDHECx3)</b>
Number of back-end ECDHE 256 curve Key exchanges  on the NetScaler appliance.

<b>ECDHE 224 curve key exchanges (BECDHECx4)</b>
Number of back-end ECDHE 224 curve Key exchanges  on the NetScaler appliance.

<b>RC4 40-bit encryptions (BRC4En4)</b>
Number of back-end RC4 40-bit cipher encryptions on the NetScaler appliance.

<b>RC4 56-bit encryptions (BRC4En5)</b>
Number of back-end RC4 56-bit cipher encryptions on the NetScaler appliance.

<b>RC4 64-bit encryptions (BRC4En6)</b>
Number of back-end RC4 64-bit cipher encryptions on the NetScaler appliance.

<b>RC4 128-bit encryptions (BRC4En1)</b>
Number of back-end RC4 128-bit cipher encryptions on the NetScaler appliance.

<b>DES 40-bit encryptions (BDESEn4)</b>
Number of back-end DES 40-bit cipher encryptions on the NetScaler appliance.

<b>DES 56-bit encryptions (BDESEn5)</b>
Number of back-end DES 56-bit cipher encryptions on the NetScaler appliance.

<b>3DES 168-bit encryptions (B3DESE1n)</b>
Number of back-end 3DES 168-bit cipher encryptions on the NetScaler appliance.

<b>AES 128-bit encryptions (BAESEn1)</b>
Back-end AES 128-bit cipher encryptions on the NetScaler appliance.

<b>AES 256-bit encryptions (BAESEn2)</b>
Back-end AES 256-bit cipher encryptions on the NetScaler appliance.

<b>RC2 40-bit encryptions (BRC2En4)</b>
Number of back-end RC2 40-bit cipher encryptions on the NetScaler appliance.

<b>RC2 56-bit encryptions (BRC2En5)</b>
Number of back-end RC2 56-bit cipher encryptions on the NetScaler appliance.

<b>RC2 128-bit encryptions (BRC2En1)</b>
Number of back-end RC2 128-bit cipher encryptions on the NetScaler appliance.

<b>null encryptions (BNullEn)</b>
Number of back-end null cipher encryptions on the NetScaler appliance.

<b>MD5 hashes (BMD5Hsh)</b>
Number of back-end MD5 hashes on the NetScaler appliance.

<b>SHA hashes (BSHAHsh)</b>
Number of back-end SHA hashes on the NetScaler appliance.

<b>SSLv3 handshakes (BSSL3Hs)</b>
Number of back-end SSLv3 handshakes on the NetScaler appliance.

<b>TLSv1 handshakes (BTLS1Hs)</b>
Number of back-end TLSv1 handshakes on the NetScaler appliance.

<b>SSLv3 client authentications (BSSL3CAt)</b>
Number of back-end SSLv3 client authentications on the NetScaler appliance.

<b>TLSv1 client authentications (BTLS1CAt)</b>
Number of back-end TLSv1 client authentications on the NetScaler appliance.

<b>RSA authentications (BRSAAt)</b>
Number of back-end RSA authentications on the NetScaler appliance.

<b>DH authentications (BDHAt)</b>
Number of back-end DH authentications on the NetScaler appliance.

<b>DSS authentications (BDSSAt)</b>
Number of back-end DSS authentications on the NetScaler appliance.

<b>Null authentications (BNullAt)</b>
Number of back-end null authentications on the NetScaler appliance.

<b>RSA key exchanges offloaded (RSAkxOf)</b>
Number of RSA key exchanges offloaded to the cryptography card.

<b>RSA sign operations offloaded (RSASnOf)</b>
Number of RSA sign operations offloaded to the cryptography card.

<b>DH key exchanges offloaded (DHkxOf)</b>
Number of DH key exchanges offloaded to the cryptography card.d

<b>RC4 encryptions offloaded (RC4EnOf)</b>
Number of RC4 encryptions offloaded to the cryptography card.

<b>DES encryptions offloaded (DESEnOf)</b>
Number of DES encryptions offloaded to the cryptography card.

<b>AES encryptions offloaded (AESEnOf)</b>
Number of AES encryptions offloaded to the cryptography card.

<b>AES-GCM 128-bit encryptions offloaded (AESGCMEnOf1)</b>
Number of AES-GCM 128-bit encryptions offloaded to the cryptography card.

<b>AES-GCM 256-bit encryptions offloaded (AESGCMEnOf2)</b>
Number of AES-GCM 256-bit encryptions offloaded to the cryptography card.

<b>Bytes encrypted in hardware (EncHw)</b>
Number of bytes encrypted in hardware.

<b>Bytes encrypted in software. (EncSw)</b>
Number of bytes encrypted in software.

<b>Bytes encrypted on the front end. (EncFe)</b>
Number of bytes encrypted on the front end.

<b>Bytes encrypted in hardware on the front end. (EncHwFe)</b>
Number of bytes encrypted in hardware on the front end.

<b>Bytes encrypted in software on front-end (EncSwFe)</b>
Number of bytes encrypted in software on the front end.

<b>Bytes encrypted on back-end (EncBe)</b>
Number of bytes encrypted on the back end.

<b>Bytes encrypted in hardware on back-end (EncHwBe)</b>
Number of bytes encrypted in hardware on the back end.

<b>Bytes encrypted in software on back-end (EncSwBe)</b>
Number of bytes encrypted in software on the back end.

<b>Bytes decrypted in hardware (DecHw)</b>
Number of bytes decrypted in hardware.

<b>Bytes decrypted in software (DecSw)</b>
Number of bytes decrypted in software.

<b>Bytes decrypted on front-end (DecFe)</b>
Number of bytes decrypted on the front end.

<b>Bytes decrypted in hardware on front-end (DecHwFe)</b>
Number of bytes decrypted in hardware on the front end.

<b>Bytes decrypted in software on front-end (DecSwFe)</b>
Number of bytes decrypted in software on the front end.

<b>Bytes decrypted on back-end (DecBe)</b>
Number of bytes decrypted on the back end.

<b>Bytes decrypted in hardware on back-end (DecHwBe)</b>
Number of bytes decrypted in hardware on the back end.

<b>Bytes decrypted in software on the back end. (DecSwBe)</b>
Number of bytes decrypted in software on back-end

<b>Backend SSL sessions reused (BSeRe)</b>
Number of back-end SSL sessions reused on the NetScaler appliance.

<b>IDEA 128-bit encryptions (IDEAEn1)</b>
Number of IDEA 128-bit cipher encryptions on the NetScaler appliance.

<b>IDEA 128-bit encryptions (BIDEAEn1)</b>
Number of back-end IDEA 128-bit cipher encryptions on the NetScaler appliance.



