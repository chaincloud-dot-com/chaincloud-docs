.. _cold-receiving-api:

********************************************************************************
Cold Receiving API
********************************************************************************

Address Txs
-----------

    **GET /api/v1/open/address/** *(str: address)* **/tx**

        Returns all txs for specific address.

        **Example response**::

            [
                {
                    "tx_hash": "a8e4f0a01a89c6335369b70d8272133164c0d29f91ac9eceddee708eb77347b1",
                    "tx_at": "2016-07-27T09:07:39",
                    "confirm_at": "2016-07-27T09:55:47",
                    "confirmation": 869,
                    "value": -20000
                },
                {
                    "tx_hash": "50369615dac8c30ac629d567bac457de59c8aa39946856bf79269b92c83478c0",
                    "tx_at": "2016-07-27T05:48:11",
                    "confirm_at": "2016-07-27T05:22:22",
                    "confirmation": 891,
                    "value": 90000
                },
                {
                    "tx_hash": "1c56ac562ad216f3fe68e8142a7f28f4889886065cc77745af4c9ddaee17c6e1",
                    "tx_at": "2016-07-27T02:21:53",
                    "confirm_at": "2016-07-27T02:31:34",
                    "confirmation": 908,
                    "value": 10000
                }
            ]

        **Parameters**:
            * ``address`` *(required)* *(str)* - specific address.

        .. note:: You can use this API to monitoring all your Cold Receiving addresses.
