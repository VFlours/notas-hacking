## Description
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/659efd595171e4c40378be6a2e9b7298/Addadshashanammu.zip)
	
## pistas


Solo presionamos "Tab" muchas veces para navegar entre directorios

## Solution

```

VFlours-picoctf@webshell:~$ ls                                                                                                            W;
Addadshashanammu.zip  README.txt  flag  ltdis.sh  static  warm
VFlours-picoctf@webshell:~$ file Addadshashanammu.zip 
Addadshashanammu.zip: Zip archive data, at least v1.0 to extract, compression method=store
VFlours-picoctf@webshell:~$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  
VFlours-picoctf@webshell:~$ ls
Addadshashanammu  Addadshashanammu.zip  README.txt  flag  ltdis.sh  static  warm
VFlours-picoctf@webshell:~$ cd Addadshashanammu/
VFlours-picoctf@webshell:~/Addadshashanammu$ ls
Almurbalarammi
VFlours-picoctf@webshell:~/Addadshashanammu$ cd Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
VFlours-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet
picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ strings fang-of-haynekhtnamet 
/lib64/ld-linux-x86-64.so.2
libc.so.6
puts^HHPTLH
__cxa_finalize
__libc_start_main
GLIBC_2.2.5
_ITM_deregisterTMCloneTable
__gmon_start__
_ITM_registerTMCloneTable
AWAVI
AUATL]@f.=
[]A\A]A^A_Ht
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}HWHt 1LLDAHH9u[]A\A]A^A_Ðf.*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}X"H0zRx
;*3$"                                                                                                                          Rx
GCC: (Ubuntu 7.5.0-3ubuntu1~18.04) 7.5.0                                                                                         FJ
crtstuff.c                                                                                                                         ?;*3$"D\RAC
deregister_tm_clonesA(B BB0
__do_global_dtors_aux
completed.7698
__do_global_dtors_aux_fini_array_entry5.08Tt`
frame_dummy
__frame_dummy_init_array_entry
fang-of-haynekhtnamet.c
__FRAME_END__ `e ~0+ :  "
__init_array_end         crtstuff.cderegister_tm_clones__do_global_dtors_auxcompleted.7698__do_global_dtors_aux_fini_array_entryframe_dummy__frame_dummy_init_array_entryfang-of-haynekhtna_DYNAMICRAME_END____init_array_end_DYNAMIC__init_array_start__GNU_EH_FRAME_HDR_GLOBAL_OFFSET_TABLE___libc_csu_fini_ITM_deregisterTMCloneTableputs@@GLIBC_2.2.5_edata__libc_start_main@@GLIB__init_array_startt__gmon_start____dso_handle_IO_stdin_used__libc_csu_init__bss_startmain__TMC_END___ITM_registerTMCloneTable__cxa_finalize@@GLIBC_2.2.5.symtab.strtab.shstrtab.interp.note__GNU_EH_FRAME_HDRbuild-id.gnu.hash.dynsym.dynstr.gnu.version.gnu.version_r.rela.dyn.rela.plt.init.plt.got.text.fini.rodata.eh_frame_hdr.eh_frame.init_array.fini_array.dynamic.data.bss.co_GLOBAL_OFFSET_TABLE_
__libc_csu_fini
_ITM_deregisterTMCloneTable
puts@@GLIBC_2.2.5
_edata
__libc_start_main@@GLIBC_2.2.5
__data_start
__gmon_start__
__dso_handle
_IO_stdin_used
__libc_csu_init
__bss_start
main
__TMC_END__
_ITM_registerTMCloneTable
__cxa_finalize@@GLIBC_2.2.5
.symtab
.strtab
.shstrtab
.interp
.note.ABI-tag
.note.gnu.build-id
.gnu.hash
.dynsym
.dynstr
.gnu.version
.gnu.version_r
.rela.dyn
.rela.plt
.init
.plt.got
.text
.fini
.rodata
.eh_frame_hdr
.eh_frame
.init_array
.fini_array
.dynamic
.data
.bss
.comment
VFlours-picoctf@webshell:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ strings fang-of-haynekhtnamet | grep pico   
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}

```


## notes

se utilizaron los siguientes comandos:
	1. strings
	2. grep
	3. unzip
## references
