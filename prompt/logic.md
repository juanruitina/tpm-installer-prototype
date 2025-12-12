## Logic pseudocode

  * Show error description  
  * If there is any action other than ActionContactOEM and ActionContactOSVendor  
    * Show “Try the solutions below, contact IT support, or choose a different encryption method.”  
  * Else  
    * Show “Contact IT support, or choose a different encryption method.”  
  * If action other than ActionContactOEM and ActionContactOSVendor  
    * Show accordion  
    * For every action other than ActionContactOEM and ActionContactOSVendor  
      * Set accordion item title as “Solution \[Action number (counter)\]: \[Action title\]”  
      * Show “\[Action description\] \[Action caveats\]”  
      * If ActionRebootToFWSettings  
        * Show firmware settings instructions  
      * If action involves clearing the TPM  
        * Show warning  
        * Show risk acknowledgement checkbox  
      * Show action button with action label, disabled if checkbox unchecked.  
  * Show technical details accordion


On action error, show inline error as per design

If following action is restart or power off, do automatically (user has been warned in text and action button label)

In firmware settings instructions, check device vendor (/sys/devices/virtual/dmi/id/sys\_vendor):

* Dell: (F2 or Fn \+ F2 for Dell computers)  
* Lenovo: (F2, Fn \+ F2, F1 or Enter then F1 for Lenovo computers)  
* HP: (F10 or Esc then F10 for HP computers)  
* Else: (commonly F2, F10 or Delete)