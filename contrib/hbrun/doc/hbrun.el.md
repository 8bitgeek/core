Harbour Shell / Script Runner 3\.2\.0dev \(r2013\-03\-28 03:24\)  
Copyright \(c\) 2007\-2013, Viktor Szakáts  
Copyright \(c\) 2003\-2007, Przemysław Czerpak  
<http://harbour\-project\.org/>  

Syntax:  
  
  hbrun &lt;file\[\.hb|\.prg|\.hrb|\.dbf\]&gt;|&lt;option&gt; \[&lt;παραμετρος\[ι\]&gt;\]  
  
Περιγραφή:  


  Το hbrun μπορεί να εκτελεί σενάρια Harbour  \(πηγαία ή προκατασκευασμένα\), και προσφέρει επίσης ένα διαλογικό περιβάλλον\.
  
Οι παρακάτω επιλογές είναι διαθέσιμες στη γραμμή\-εντολών:  


 - **\-\-hb:debug** Ενεργοποίηση αποσφαλμάτωσης script


 - **\-help** η παρούσα βοήθεια
 - **\-viewhelp** εκτεταμένη βοήθεια σε προβολή κειμένου
 - **\-longhelp** long help
 - **\-longhelpmd** εκτεταμένη βοήθεια σε μορφή [Markdown](http://daringfireball.net/projects/markdown/)
  
Αρχεία:  


 - **\*\.hb** Σενάριο Harbour
 - **\*\.hrb** Μεταφέρσιμο δυαδικό Harbour \(γνωστό και ως προκατασκευασμένο σενάριο\)
 - **hbstart\.hb** startup Harbour script for interactive Harbour shell\. It gets executed automatically on shell startup, if present\. Possible locations \(in order of precedence\) \[\*\]: \.\\, %APPDATA%\\\.harbour, &lt;hbrun κατάλογος&gt;
 - **shell plugins** \.hb and \.hrb plugins for interactive Harbour shell\. They may reside in \[\*\]: %APPDATA%\\\.harbour\\
 - **\.hb\_history** αποθηκεύει ιστορικό εντολών για το διαλογικό shell Harbour\. Μπορείτε να απενεργοποιήσετε το ιστορικό κάνοντας την πρώτη γραμμή 'no' \(χωρίς τα εισαγωγικά και με νεα γραμμή\)\. Βρίσκεται στο \[\*\]: %APPDATA%\\\.harbour\\
 - **hb\_extension** λίστα καταλήξεων προς φόρτωση στο διαλογικό κέλυφος του Harbour\. Μία κατάληξη ανα γραμμή, το τμήμα της γραμμής μετά από ένα χαρακτήρα '\#' αγνοείται\. Εναλλακτικά ονομα\-αρχείου στο Ms\-DOS: Το hb\_ext\.ini\. Βρίσκεται μεσα στο \[\*\]: %APPDATA%\\\.harbour\\


Προκαθορισμένες σταθερές σε πηγαία αρχεία:


 - **\_\_HBSCRIPT\_\_HBSHELL** when a Harbour source file is run as a shell script
 - **&lt;standard Harbour&gt;** \_\_PLATFORM\_\_\*, \_\_ARCH\*BIT\_\_, \_\_\*\_ENDIAN\_\_, etc\.\.\.
  
Μεταβλητές περιβάλλοντος:  


 - **HB\_EXTENSION** space separated list of extensions to load in interactive Harbour shell
  
Shell API διαθέσιμο σε σενάρια Harbour:  


 - **hbshell\_gtSelect\( \[&lt;cGT&gt;\] \) \-&gt; NIL**  
Switch GT\. Default \[\*\]: 'gtwin'
 - **hbshell\_Clipper\(\) \-&gt; NIL**  
Enable Clipper compatibility \(non\-Unicode\) mode\.
 - **hbshell\_include\( &lt;cHeader&gt; \) \-&gt; &lt;lSuccess&gt;**  
Φόρτωση Harbour header\.
 - **hbshell\_uninclude\( &lt;cHeader&gt; \) \-&gt; &lt;lSuccess&gt;**  
Αποφόρτωση Harbour header\.
 - **hbshell\_include\_list\(\) \-&gt; NIL**  
Εμφάνιση λίστας των φορτωμένων Harbour header\.
 - **hbshell\_ext\_load\( &lt;cPackageName&gt; \) \-&gt; &lt;lSuccess&gt;**  
Φόρτωση πακέτου\. Παρόμοιο με τη ντιρεκτίβα \#request PP\.
 - **hbshell\_ext\_unload\( &lt;cPackageName&gt; \) \-&gt; &lt;lSuccess&gt;**  
Αποφόρτωση πακέτου
 - **hbshell\_ext\_get\_list\(\) \-&gt; &lt;aPackages&gt;**  
List of loaded packages\.
 - **hbshell\_DirBase\(\) \-&gt; &lt;cBaseDir&gt;**  
hb\_DirBase\(\) not mapped to script\.
 - **hbshell\_ProgName\(\) \-&gt; &lt;cPath&gt;**  
hb\_ProgName\(\) not mapped to script\.
  
Notes:  


  - \.hb, \.prg, \.hrb ή \.dbf αρχείο δοσμένο ως πρώτη παραμέτρος θα εκτελεστεί σαν σενάριο Harbour\. Αν το όνομα\-αρχείου δεν περιέχει ορίσματα μονοπατιών, θα αναζητηθεί στο τρέχοντα κατάλογο εργασίας και στο  PATH\. Αν δεν δόθηκε κατάληξη, θα αναζητηθούν \.hb and \.hrb καταλήξεις, με αυτή τη σειρά\. Αρχείο \.dbf θα ανοιχτεί αυτόματα σε κατάσταση shared και θα ξεκινήσει το διαλογικό shell του Harbour\. Μη standard καταλήξεις θα ανιχνευτούν αυτομάτως για πηγαίους και προκατασεκυασμένους τυπους\. Σημειώστε, για σενάρια Harbour, η κωδικοσελίδα ορίζεται απο προεπιλογή σε  UTF\-8\. Το εξ'ορισμού βασικό αρχείο header 'hb\.ch'  συμπεριλαμβάνεται αυτόματα, δηλ\. \#included\. Προεπιλεγμένη μορφή ημερ/νίας είναι η πρότυπη κατα  ISO μορφή: εεεε\-μμ\-ηη\. Προεπιλεγμένο GT είναι το 'gtcgi', εκτός αν ανιχνευτούν CUI κλήσεις πλήρους οθόνης, οπότε επιλέγεται αυτομάτως 'gtwin' \[\*\] \(εκτός για τις INIT PROCEDUREs\)\.
  - Μπορεί να χρησιμοποιηθεί ο συνδυασμός πλήκτρων &lt;Alt\+V&gt; στο διαδραστικό shell του Harbour για επικόληση από το πρόχειρο\.
  - Τιμές με αστερίσκο \[\*\] μπορεί να εξαρτώνται από την πλατφόρμα υποδοχής ή/και τη διαμόρφωση\. Η παρούσα βοήθεια δημιουργήθηκε στην 'win' πλατφόρμα υποδοχής\.
  
Αδεια:  


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

  
Συγγραφέας:  


 - Viktor Szakáts \(harbour syenar\.net\) 
