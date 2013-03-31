Harbour Shell / Script Runner 3\.2\.0dev \(r2013\-03\-28 03:24\)  
Copyright \(c\) 2007\-2013, Viktor Szakáts  
Copyright \(c\) 2003\-2007, Przemysław Czerpak  
<http://harbour\-project\.org/>  

Syntax:  
  
  hbrun &lt;file\[\.hb|\.prg|\.hrb|\.dbf\]&gt;|&lt;option&gt; \[&lt;π  
�ρ  
�  
�  
�τρ  
�ς\[  
�\]&gt;\]  
  
  
�  
�ρ  
�  
�ρ  
�φ  
�:  


    
�  
� hbrun   
�π  
�ρ  
�  
�   
�  
�   
�  
�τ  
�  
�  
�  
� σ  
�  
�  
�ρ  
�  
� Harbour  \(π  
�  
�  
�  
�  
�   
� πρ  
�  
�  
�τ  
�σ  
�  
�υ  
�σ  
�  
�  
�  
�\),   
�  
�  
� πρ  
�σφ  
�ρ  
�  
�   
�π  
�σ  
�ς   
�  
�  
�   
�  
�  
�  
�  
�  
�  
�  
�ό π  
�ρ  
�  
�  
�  
�  
�  
�  
�\.
  
  
�  
� π  
�ρ  
�  
�  
�τω   
�π  
�  
�  
�  
�  
�ς   
�  
�  
�  
�  
�   
�  
�  
�  
�  
�σ  
�  
�  
�ς στ  
�   
�ρ  
�  
�  
�  
�\-  
�  
�τ  
�  
�ώ  
�:  


 - **\-\-hb:debug**   
�  
�  
�ρ  
�  
�π  
�  
�  
�σ  
�   
�π  
�σφ  
�  
�  
�  
�τωσ  
�ς script


 - **\-help**   
� π  
�ρ  
�ύσ  
�   
�  
�  
�  
�  
�  
�  
�
 - **\-viewhelp**   
�  
�τ  
�τ  
�  
�  
�  
�  
�   
�  
�  
�  
�  
�  
�  
� σ  
� πρ  
�  
�  
�  
�  
�   
�  
�  
�  
�  
�  
�  
�υ
 - **\-longhelp** long help
 - **\-longhelpmd**   
�  
�τ  
�τ  
�  
�  
�  
�  
�   
�  
�  
�  
�  
�  
�  
� σ  
�   
�  
�ρφ  
� [Markdown](http://daringfireball.net/projects/markdown/)
  
  
�ρχ  
�  
�  
�:  


 - **\*\.hb**   
�  
�  
�  
�ρ  
�  
� Harbour
 - **\*\.hrb**   
�  
�τ  
�φ  
�ρσ  
�  
�  
�   
�υ  
�  
�  
�  
�ό Harbour \(  
�  
�ωστό   
�  
�  
� ως πρ  
�  
�  
�τ  
�σ  
�  
�υ  
�σ  
�  
�  
�  
� σ  
�  
�  
�ρ  
�  
�\)
 - **hbstart\.hb** startup Harbour script for interactive Harbour shell\. It gets executed automatically on shell startup, if present\. Possible locations \(in order of precedence\) \[\*\]: \.\\, %APPDATA%\\\.harbour, &lt;hbrun   
�  
�τ  
�  
�  
�  
�  
�ς&gt;
 - **shell plugins** \.hb and \.hrb plugins   
�  
�  
� τ  
�   
�  
�  
�  
�  
�  
�  
�  
�ό   
�  
�  
�υφ  
�ς τ  
�υ Harbour\.   
�ρ  
�π  
�  
�   
�  
�   
�ρ  
�σ  
�  
�  
�τ  
�  
�   
�  
�σ  
� στ  
� \[\*\]: %APPDATA%\\\.harbour\\
 - **\.hb\_history**   
�π  
�  
�  
�  
�  
�ύ  
�  
�   
�στ  
�ρ  
�  
�ό   
�  
�τ  
�  
�ώ  
�   
�  
�  
� τ  
�   
�  
�  
�  
�  
�  
�  
�  
�ό shell Harbour\.   
�π  
�ρ  
�  
�τ  
�   
�  
�   
�π  
�  
�  
�ρ  
�  
�π  
�  
�  
�σ  
�τ  
� τ  
�   
�στ  
�ρ  
�  
�ό   
�  
�  
�  
�  
�τ  
�ς τ  
�  
� πρώτ  
�   
�ρ  
�  
�  
�  
� 'no' \(χωρ  
�ς τ  
�   
�  
�σ  
�  
�ω  
�  
�  
�  
�   
�  
�  
�   
�  
�   
�  
�  
�   
�ρ  
�  
�  
�  
�\)\.   
�ρ  
�σ  
�  
�τ  
�  
� στ  
� \[\*\]: %APPDATA%\\\.harbour\\
 - **hb\_extension**   
�  
�στ  
�   
�  
�τ  
�  
�  
�  
�  
�ω  
� πρ  
�ς φόρτωσ  
� στ  
�   
�  
�  
�  
�  
�  
�  
�  
�ό   
�  
�  
�υφ  
�ς τ  
�υ Harbour\.   
�  
�  
�   
�  
�τ  
�  
�  
�  
�  
�   
�  
�  
�   
�ρ  
�  
�  
�  
�, τ  
� τ  
�  
�  
�  
� τ  
�ς   
�ρ  
�  
�  
�  
�ς   
�  
�τ  
�   
�πό   
�  
�  
� χ  
�ρ  
�  
�τ  
�ρ  
� '\#'   
�  
�  
�  
�  
�  
�τ  
�  
�\.   
�  
�  
�  
�  
�  
�  
�τ  
�  
�  
�   
�  
�  
�  
�  
�\-  
�ρχ  
�  
�  
�υ στ  
� Ms\-DOS:   
�  
� hb\_ext\.ini\.   
�ρ  
�σ  
�  
�τ  
�  
�   
�  
�σ  
� στ  
� \[\*\]: %APPDATA%\\\.harbour\\


  
�ρ  
�  
�  
�  
�  
�ρ  
�σ  
�  
�  
�  
�ς στ  
�  
�  
�ρ  
�ς σ  
� π  
�  
�  
�  
�  
�   
�ρχ  
�  
�  
�:


 - **\_\_HBSCRIPT\_\_HBSHELL** when a Harbour source file is run as a shell script
 - **&lt;standard Harbour&gt;** \_\_PLATFORM\_\_\*, \_\_ARCH\*BIT\_\_, \_\_\*\_ENDIAN\_\_, etc\.\.\.
  
  
�  
�τ  
�  
�  
�  
�τ  
�ς π  
�ρ  
�  
�  
�  
�  
�  
�  
�τ  
�ς:  


 - **HB\_EXTENSION**   
�  
�στ  
�   
�  
�τ  
�  
�  
�  
�  
�ω  
�,   
�  
�  
�χωρ  
�σ  
�  
�  
�ω  
�   
�  
�   
�  
�  
�ό   
�  
�  
�στ  
�  
�  
�, πρ  
�ς φόρτωσ  
� στ  
�   
�  
�  
�  
�  
�  
�  
�  
�ό   
�  
�  
�υφ  
�ς τ  
�υ Harbour 
  
Shell API   
�  
�  
�  
�  
�σ  
�  
�  
� σ  
� σ  
�  
�  
�ρ  
�  
� Harbour:  


 - **hbshell\_gtSelect\( \[&lt;cGT&gt;\] \) \-&gt; NIL**  
Switch GT\. Default \[\*\]: 'gtwin'
 - **hbshell\_Clipper\(\) \-&gt; NIL**  
Enable Clipper compatibility \(non\-Unicode\) mode\.
 - **hbshell\_include\( &lt;cHeader&gt; \) \-&gt; &lt;lSuccess&gt;**  
  
�όρτωσ  
� Harbour header\.
 - **hbshell\_uninclude\( &lt;cHeader&gt; \) \-&gt; &lt;lSuccess&gt;**  
  
�π  
�φόρτωσ  
� Harbour header\.
 - **hbshell\_include\_list\(\) \-&gt; NIL**  
  
�  
�φ  
�  
�  
�σ  
�   
�  
�στ  
�ς τω  
� φ  
�ρτω  
�  
�  
�ω  
� Harbour header\.
 - **hbshell\_ext\_load\( &lt;cPackageName&gt; \) \-&gt; &lt;lSuccess&gt;**  
  
�όρτωσ  
� π  
�  
�  
�τ  
�υ\.   
�  
�ρό  
�  
�  
�  
�   
�  
� τ  
�   
�τ  
�ρ  
�  
�τ  
�  
�  
� \#request PP\.
 - **hbshell\_ext\_unload\( &lt;cPackageName&gt; \) \-&gt; &lt;lSuccess&gt;**  
  
�π  
�φόρτωσ  
� π  
�  
�  
�τ  
�υ
 - **hbshell\_ext\_get\_list\(\) \-&gt; &lt;aPackages&gt;**  
List of loaded packages\.
 - **hbshell\_DirBase\(\) \-&gt; &lt;cBaseDir&gt;**  
hb\_DirBase\(\) not mapped to script\.
 - **hbshell\_ProgName\(\) \-&gt; &lt;cPath&gt;**  
hb\_ProgName\(\) not mapped to script\.
  
Notes:  


  - \.hb, \.prg, \.hrb   
� \.dbf   
�ρχ  
�  
�  
�   
�  
�σ  
�  
�  
�  
� ως πρώτ  
� π  
�ρ  
�  
�  
�τρ  
�ς   
�  
�   
�  
�τ  
�  
�  
�στ  
�  
� σ  
�  
� σ  
�  
�  
�ρ  
�  
� Harbour\.   
�  
� τ  
� ό  
�  
�  
�  
�\-  
�ρχ  
�  
�  
�υ   
�  
�  
� π  
�ρ  
�  
�χ  
�  
�   
�ρ  
�σ  
�  
�τ  
�   
�  
�  
�  
�π  
�τ  
�ώ  
�,   
�  
�   
�  
�  
�  
�  
�τ  
�  
�  
�  
� στ  
� τρ  
�χ  
�  
�τ  
�   
�  
�τ  
�  
�  
�  
�  
�   
�ρ  
�  
�σ  
�  
�ς   
�  
�  
� στ  
�  PATH\.   
�  
�   
�  
�  
�   
�ό  
�  
�  
�  
�   
�  
�τ  
�  
�  
�  
�  
�,   
�  
�   
�  
�  
�  
�  
�τ  
�  
�  
�ύ  
� \.hb and \.hrb   
�  
�τ  
�  
�  
�  
�  
�  
�ς,   
�  
�   
�υτ  
� τ  
� σ  
�  
�ρ  
�\.   
�ρχ  
�  
�  
� \.dbf   
�  
�   
�  
�  
�  
�χτ  
�  
�   
�υτό  
�  
�τ  
� σ  
�   
�  
�τ  
�στ  
�σ  
� shared   
�  
�  
�   
�  
�   
�  
�  
�  
�  
�  
�σ  
�  
� τ  
�   
�  
�  
�  
�  
�  
�  
�  
�ό shell τ  
�υ Harbour\.   
�  
� standard   
�  
�τ  
�  
�  
�  
�  
�  
�ς   
�  
�   
�  
�  
�χ  
�  
�υτ  
�ύ  
�   
�υτ  
�  
�  
�τως   
�  
�  
� π  
�  
�  
�  
�  
�υς   
�  
�  
� πρ  
�  
�  
�τ  
�σ  
�  
�υ  
�σ  
�  
�  
�  
�υς τυπ  
�υς\.   
�  
�  
�  
�  
�ώστ  
�,   
�  
�  
� σ  
�  
�  
�ρ  
�  
� Harbour,   
�   
�ω  
�  
�  
�  
�σ  
�  
�  
�  
�  
�   
�ρ  
�  
�  
�τ  
�  
�   
�π  
� πρ  
�  
�π  
�  
�  
�  
�  
� σ  
�  UTF\-8\.   
�  
�   
�  
�'  
�ρ  
�σ  
�  
�ύ   
�  
�σ  
�  
�ό   
�ρχ  
�  
�  
� header 'hb\.ch'  συ  
�π  
�ρ  
�  
�  
�  
�  
�  
�  
�  
�τ  
�  
�   
�υτό  
�  
�τ  
�,   
�  
�  
�\. \#included\.   
�ρ  
�  
�π  
�  
�  
�  
�  
�  
�  
�  
�   
�  
�ρφ  
�   
�  
�  
�ρ/  
�  
�  
�ς   
�  
�  
�  
�  
�   
� πρότυπ  
�   
�  
�τ  
�  ISO   
�  
�ρφ  
�:   
�  
�  
�  
�\-  
�  
�\-  
�  
�\.   
�ρ  
�  
�π  
�  
�  
�  
�  
�  
�  
�  
� GT   
�  
�  
�  
�  
� τ  
� 'gtcgi',   
�  
�τός   
�  
�   
�  
�  
�χ  
�  
�υτ  
�ύ  
� CUI   
�  
�  
�σ  
�  
�ς π  
�  
�ρ  
�υς   
�  
�ό  
�  
�ς,   
�πότ  
�   
�π  
�  
�  
�  
�  
�τ  
�  
�   
�υτ  
�  
�  
�τως 'gtwin' \[\*\] \(  
�  
�τός   
�  
�  
� τ  
�ς INIT PROCEDUREs\)\.
  -   
�π  
�ρ  
�  
�   
�  
� χρ  
�σ  
�  
�  
�π  
�  
�  
�  
�  
�  
�   
� συ  
�  
�υ  
�σ  
�ός π  
�  
�  
�τρω  
� &lt;Alt\+V&gt; στ  
�   
�  
�  
�  
�ρ  
�στ  
�  
�ό shell τ  
�υ Harbour   
�  
�  
�   
�π  
�  
�ό  
�  
�σ  
�   
�πό τ  
� πρόχ  
�  
�ρ  
�\.
  -   
�  
�  
�  
�ς   
�  
�   
�στ  
�ρ  
�σ  
�  
� \[\*\]   
�π  
�ρ  
�  
�   
�  
�   
�  
�  
�ρτώ  
�τ  
�  
�   
�πό τ  
�  
� π  
�  
�τφόρ  
�  
� υπ  
�  
�  
�χ  
�ς   
�/  
�  
�  
� τ  
�   
�  
�  
�  
�όρφωσ  
�\.   
� π  
�ρ  
�ύσ  
�   
�  
�  
�  
�  
�  
�  
�   
�  
�  
�  
�  
�υρ  
�  
�  
�  
�  
�  
� στ  
�  
� 'win' π  
�  
�τφόρ  
�  
� υπ  
�  
�  
�χ  
�ς\.
  
  
�  
�  
�  
�  
�:  


  This program is free software; you can redistribute it and/or modify  
it under the terms of the GNU General Public License as published by  
the Free Software Foundation; either version 2 of the License, or  
\(at your option\) any later version\.  
  
This program is distributed in the hope that it will be useful,  
but WITHOUT ANY WARRANTY; without even the implied warranty of  
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE\.  See the  
GNU General Public License for more details\.  
  
You should have received a copy of the GNU General Public License  
along with this program; if not, write to the Free Software  
Foundation, Inc\., 675 Mass Ave, Cambridge, MA 02139, USA \(or visit  
their web site at http://www\.gnu\.org/\)\.  
  
License extensions:  
  \- This source code must be kept and distributed as part  
    of the Harbour package and/or the placement of the tool sources  
    and files must reflect that it is part of Harbour Project\.  
  \- Copyright information must always be presented by  
    projects including this tool or help text\.  
  \- Modified versions of the tool must clearly state this  
    fact on the copyright screen\.  
  \- Source code modifications shall always be made available  
    along with binaries\.  
  \- Help text and documentation is licensed under  
    Creative Commons Attribution\-ShareAlike 3\.0:  
    http://creativecommons\.org/licenses/by\-sa/3\.0/  

  
  
�υ  
�  
�ρ  
�φ  
�  
�ς:  


 - Viktor Szakáts \(harbour syenar\.net\) 
