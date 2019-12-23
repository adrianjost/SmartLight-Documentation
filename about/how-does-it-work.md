# How does it work?

{% hint style="success" %}
All communication that contains user data is secured by HTTPs.   
The insecure ws connection will keep inside your local network and will not be accessible from the outside.
{% endhint %}

![](../.gitbook/assets/smartlight-v3-information-flow.png)

Unfortunately it is not possible to server the webpage over HTTPs, because then all local requests to the ESPs would be blocked by the browsers security policy which disallows mixed content. That is why the actual website is served over HTTP. To use HTTPs, a completly different architecture would be required that exposes the ESPs to the world wide web. With the current architecture, all communication to the ESPs is 100% local and the network traffic will never leave your home network.

