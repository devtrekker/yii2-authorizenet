YII2 Authorizenet Gateway Extensions
====================================
YII2 Authorizenet Payment Gateway Extension

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist devtrekker/yii2-authorizenet "*"
```

or add

```
"devtrekker/yii2-authorizenet": "*"
```

to the require section of your `composer.json` file.

Dependencies
-------------
This package depends on the following packages:

  - phpoption/phpoption (1.5.0)
  - phpcollection/phpcollection (0.5.0)
  - jms/serializer (1.11.0)
  - jms/parser-lib (1.0.0)
  - jms/metadata (1.6.0)
  - goetas-webservices/xsd2php-runtime (v0.2.8)
  - doctrine/lexer (v1.0.1)
  - doctrine/annotations (v1.2.7)
  - authorizenet/authorizenet (1.9.3)


How to call?
-----	
You just have to include any of the class in your code before using it and other code you can use exactly the same as authorizenet PHP SDK.
	
	use AuthorizeNetAIM;
	use AuthorizeNetARB;
	use AuthorizeNetCIM;
	use AuthorizeNetCP;
	use AuthorizeNetDPM;
	use AuthorizeNetSIM;
	use AuthorizeNetSOAP;
	use AuthorizeNetTD;
	


Usage Examples
-----
Once the extension is installed, simply use it in your code by  :

````php
	use AuthorizeNetAIM;
	define("AUTHORIZENET_API_LOGIN_ID", "YOURLOGIN");
	define("AUTHORIZENET_TRANSACTION_KEY", "YOURKEY");
	define("AUTHORIZENET_SANDBOX", true);

	$sale = new AuthorizeNetAIM;
	$sale->amount = "5.99";
	$sale->card_num = '4111111111111111';
	$sale->exp_date = '0418';
	$response = $sale->authorizeAndCapture();
	if ($response->approved) {
		echo "Success! Transaction ID:" . $response->transaction_id;
	} else {
		echo "ERROR:" . $response->error_message;
	}	
````

For more examples visit https://github.com/AuthorizeNet/sdk-php	
	
## Credits

This package is based on original work by tenbulls/yii2-authorizenet, which is not longer available.
    
## License

**yii2-authorizenet** is released under the BSD 3-Clause License. See the bundled `LICENSE.md` for details.	
	
