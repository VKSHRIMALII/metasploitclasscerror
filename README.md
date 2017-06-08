# metasploitclasscerror SOlution 
Metasploit Missing MetasploitC lass Compatibility Error  
I have  seen a problem couple of time that people cant load this exploit downlaod from exploit-db, rapid7 or any other source 

they get this following error like: 

/root/.msf5/modules/exploits/windows/exploit.rb: Msf::Modules::MetasploitClassCompatibilityError Failed to load module (windows/42134 from /root/.msf5/modules/exploits/windows/42134.rb) due to Missing compatible Metasploit<major_version> class constant

or simplar type of error says that :
               
							 Msf::Modules::MetasploitClassCompatibilityError Failed to load module......................................... ..................due to Missing compatible Metasploit<major_version> class constant
							 
							 
you have seen couple of solutions but none of them is perfectly working now i have fix solution for this
when you look inside error you can see erorr is comming "due to missing compatible Metasploit<major_version>  class constant"


to resolve this error you have to make your exploit compatible with new Metasploitclass for that you have to change following chanegs 


open downloaded exploit and check for 
            class MetasploitModule < Msf::Exploit::Remote
Replace this class MetasploitModule with following code 

class Metasploit3 < Msf::Exploit::Remote
now save your file and goto msfconsole it will work 
