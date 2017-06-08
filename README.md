# metasploitclasscerror Solution
# Metasploit Missing MetasploitC lass Compatibility Error  

I have seen a problem couple of times that people can't load downloaded exploit  from exploit-DB, rapid7 or any other source 
 
 They get thefollowing error like while running mefconsole or metasploit :  

/root/.msf5/modules/exploits/windows/exploit.rb: Msf::Modules::MetasploitClassCompatibilityError Failed to load module (windows/42134 from /root/.msf5/modules/exploits/windows/42134.rb) due to Missing compatible Metasploit<major_version> class constant

or simplar type of error says that 
...................................Msf::Modules::MetasploitClassCompatibilityError Failed to load module......................................... ..................due to Missing compatible Metasploit<major_version> class constant
							 
							 
you have seen couple of solutions but none of them is perfectly working now i have find solution for this issue 
when you look inside error you can see erorr is comming "due to missing compatible Metasploit<major_version>  class constant"
to resolve this error you have to make your exploit compatible with new Metasploit class for that you have to d0 following chanegs 


1. open downloaded exploit and check for 
             # class MetasploitModule < Msf::Exploit::Remote
2. Replace this class MetasploitModule with following code 

             # class Metasploit3 < Msf::Exploit::Remote
	     
3. now save your file and goto msfconsole it will work or reload_all
