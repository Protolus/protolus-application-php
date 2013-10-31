protolus-application-php
===========
A wrapper for protolus for web delivery

Usage
-----
The main class for web delivery is WebApplication.class.php. Wraps a number of built-in php functions as well as some framework specific functionality.

1. **php variables**
	WebApplication can be used as a wrapper for built in php variables for $\_GET, $\_REQUEST and $\_COOKIE. As well as your session handler. 
	
	Get andsSet $\_GET:

		WebApplication::setGet("var", $some_var);
		$get_var = WebApplication::getGet("var");

	Equivalent to:

		$_GET['var'] = $some_var;
		$get_var = $_GET['var'];
	Get and set $\_COOKIE:

		$cookie_var = WebApplication::getCookie("cookie_var");
	Equivalent to:

		$cookie_var = $_COOKIE["cookie_var"];

	Session:

		$session_var = WebApplication::getSession("sesion_var");
		WebApplication::setSession("session_var", "value");

	note: using WebApplications 'get' function will check the $\_SESSION, $\_SERVER and $\_ENV for a specific variable. 

		$some_var = WebApplication::get("some_var");
	with an optional second parameter, which set to true will check $\_REQUEST, $\_COOKIE, $\_SESSION, $\_SERVER, $\_ENV

		$some_other_var = WebApplication::get("some_var", true);
2. **configuration** 
	Allows you to access variables set in your configuration file.

		$config_var = WebApplication::getConfiguration("application.config_var");


Enjoy,

The Protolus Team