MySipIsOnFire
=============

Usage to make a call (other methods available, more docs at http://code.google.com/p/php-sip/):
```
try {
				$api = new MySipIsOnFire\Sip();
				$api->setDebug(true);

				// if your SIP service doesn't accept anonymous inbound calls use the two lines below
				$api->setUsername('username');
				$api->setPassword('password');

				$api->addHeader('Subject: MySubject');
				$api->setMethod('INVITE');
				$api->setFrom('sip:username@'.$api->getSrcIp());
				$api->setUri('sip:NumberIWantToDial@mysipserveraddress.com:5060');

				$res = $api->send();
				var_dump($res);
} catch(Exception $e) {
				echo "Oops...";
}
```
