.. _what-is-v-device:

********************************************************************************
What is V-Device?
********************************************************************************

V-Device is like a "2-Step Verification" Device for you.

V-Device is an Android device running with ChainCloud-V (an Open Source App developped by us). With this App, you can establish a secured channel between your V-Device and ChainCloud's HSM-Cold Model with SMS. All data transfered on this channel should be verified to ensure the security.

There are two different verifications between V-Device and ChainCloud HSM-Cold Model:

* All Hot-Sending requests (from your website/service) shoud be signed by your V Device, and the signature will pass through ChainCloud API to HSM-Hot Device, and then to HSM-Cold Model. After that, the HSM-Cold Model will verify the signature with data. If the signature is correct, HSM-Cold will acknowlege the Hot-Sending request, otherwise, it will close the channel and notify the administrator.
* When you request the Cold-Receiving/Hot-Sending addresses from ChainCloud API, and plan to use these addresses in your business logic, you can verify each batch of these addresses (1000 address per batch) with the security channel between V Device and HSM-Cold Model. You should verify all addresses before use, to protect your blockchain assets.

You can also develop your own version of ChainCloud-V (because it is Open Source), and add other safe strategies, for example :

* Limitation of destination addresses;
* Strategies of sending amount;
* Strategies of sending frequency;
* Special encryption strategy between your website/service and your V Device;

