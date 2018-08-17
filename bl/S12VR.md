###Key Points
- IVBR = 0xE6; // Interrupt vectot table relocate to 0xE600
- App_Start_Adress = 0xFFFE; (*(unsigned int *)(App_Start_Adress) // Content stored at this address is application start address


LIN_communication
File_transfer line by line
S12 vector relocate
don't use vector number in mcu.h ,in linker files define vector area and set vector entry

	VECTORS       = READ_ONLY     0xE600 TO   0xE6FF; /*intentionally not defined: used for VECTOR commands below*/ 
	//OSVECTORS      = READ_ONLY     0xFF80 TO   0xFFFF;   /* OSEK interrupt vectors (use your vector.o) */
	
	ENTRIES /* keep the following unreferenced variables */
	_vectab
	END

In boot program relocate Flash operation function to RAM and set function entry

	ENTRIES /* keep the following unreferenced variables */
	PFlash_Program
	PFlash_EraseSector
	PFlash_EraseSectorBySector 
	END

