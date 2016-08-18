.. _v-device-sample:

********************************************************************************
V-Device Sample
********************************************************************************

In following docs, we will describe how to build up a web-service that can be used by V-Device

V-Test
================================================================================

Get A Tx To Be Send
----------------------

    **GET /api/v1/open/vtest**

        Get A Tx To Be Send.

        **Example response**::

            {
                "vtest_info": "B23A7DDF7AF953D4344ED8B190E9424C2A8D85CAA00B4358D58C5341E36A194097EA21F7D457E770E2C9512834D206DE9EB766ED154F7ECEABB61056E97D200F174EAD69CF62E5A7EDDF823AB8293EAEDFA47AA1FF66D1FDF2D4D2B6FFC0DF5E1D62DB84C7A3C6E432CDE0CDEABB9C79/166EAB021AFB6244191EEE75340F8109/D267F338A21B487D",
                "vtest_at": "2016-08-18T06:00:53",
                "vtest_id": 11
            }

        .. note::
            * ``vtest_info`` encrypt with aes. decryption is {"outs":"1NbbvxBYxGGCBhaM8mow1HFWA7dB5yukmY,10000;1MCs9SZwLg9JvLo6pzvVBWtmSV1dakwyM1,10000","dynamic":0}

Update A Tx Status
----------------------

    **POST /api/v1/open/vtest**

        Update A Tx Status

        **Example response**::

            {
                "result": true
            }

        **Parameters**:
            * ``vtest_id`` *(required)* *(string)* - coin type, for example *(BTC)*.
            * ``tx_hash`` *(optional)* *(string)* - tx hash.

        .. note::
            * ``tx_hash`` if hash is null, it is failed, else success.
