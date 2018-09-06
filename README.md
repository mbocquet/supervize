**supervize** gives an "as fast as you can reach" view of device(s) and service(s) availability. Its purpose is to check things during changes to see if you don't break those things !

# Usage

## For one device

Suppose you have a device on your network and you want to monitor the availability of the following ports ; ssh, http, https. You should use this command :

`watch 'echo device 10.11.12.13|supervize /dev/stdin ssh http https'`

If you prefer numbers...

`watch 'echo device 10.11.12.13|supervize /dev/stdin 22 80 443'`

## For many devices

Now if you want to monitor many devices, create a file for example devices.supervize... or whatever you like as name.

<pre>
device1		10.11.12.13
device2		device2
...			...
deviceN		deviceN.domain.tld
</pre>

And call supervize with the file and the ports you want to check

`watch supervize devices.supervize ssh http https`
