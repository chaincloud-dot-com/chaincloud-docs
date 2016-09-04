.. _general-usage:

********************************************************************************
General Usage
********************************************************************************

How to use ChainCloud API?

Access Method
================================================================================

Domain: **chaincloud-api.getcai.com** (api.chaincloud.com in the future)

All API should be accessed with ``token`` (in HTTP header), and you can apply for your API token `here <http://chaincloud.com>`_.

Access Samples
================================================================================

Python:

::

    domain = 'chaincloud-api.getcai.com'
    url = 'https://' + domain + '/api/v1/open/time'
    token = '3333bd0af3a28d0c18b32206627ac1af68dc63e304b9975f08917c53831a6666'
    request = urllib2.Request(url)
    request.add_header('token', token)
    response = urllib2.urlopen(request, timeout=global_timeout)

Curl:

::

    curl -H "token:3333bd0af3a28d0c18b32206627ac1af68dc63e304b9975f08917c53831a6666" https://chaincloud-api.getcai.com/api/v1/open/time

API call rate limit
================================================================================

We will set limits in the future.

