# Objective
Use BurpSuite's `Intruder` tool to perform Brute Force attacks

# Useful Links
* [http://testphp.vulnweb.com/login.php](http://testphp.vulnweb.com/login.php)

# Main
`Intruder` is a very useful tool in BurpSuite that allows you to send multiple HTTP requests in an automated way. To use it, you need to parameterize a part of the request script. `Intruder` will then make a series of requests by iterating through a range of values within a payload.

To obtain a template of the HTTP request, perform a login attempt at [http://testphp.vulnweb.com/login.php](http://testphp.vulnweb.com/login.php), as we did in [/main/repeater](http://testphp.vulnweb.com/login.php):

<img src="1.png" width="450">

Now send this script to `Intruder` by clicking `Action > Send to Intruder`:

<img src="3.png" width="850">

In the `Intruder` section, you will find the HTTP request:

<img src="4.png" width="850">

The parts of the text that are parameterized are delimited by section signs `§`. You can add section signs to the text by clicking `Add §`. Set the username as parameterized, and fix the password to the correct value, which is `test`:

<img src="5.png" width="850">

In the `Payloads` subsection, you can attach the wordlists from which you want `Intruder` to read:

<img src="6.png" width="850">

We inserted three values: `aaa, bbb, test`

<img src="7.png" width="850">

Now you can proceed with the attack by clicking `Start Attack`:

<img src="7.png" width="850">

You will see a request for each value inserted as a payload. By clicking on the record, you can read the request and the response. You can see that the third record, having the correct credentials `test:test`, has a response of a different length than the other two.