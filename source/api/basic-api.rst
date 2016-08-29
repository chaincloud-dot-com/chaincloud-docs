.. _basic-api:

********************************************************************************
Basic API
********************************************************************************

All basic APIs.

Time
----

    **GET /api/v1/open/time**

        Returns Server Time.

        **Example response**::

            {
                "time": "2016-08-02T12:51:34.460394"
            }

User
----

    **GET /api/v1/open/user**

        Returns Current User's Information.

        **Example response**::

            {
                "can_otc_ad": 0,
                "user_id": 40000,
                "gender": 0,
                "user_type": 4,
                "real_name": null,
                "receiving_index": 1,
                "avatar": null,
                "register_at": "2016-07-11T14:19:55",
                "address": "1Mzvo2UkBnEpQC8xkui23mYQQeL8NREqrJ",
                "balance": 60000,
                "user_name": "bitpie-hot-40000",
                "can_otc_order": 0
            }

Address Batch
-------------

    **GET /api/v1/open/address/batch/** *(int: batch_no)*

        Returns a batch of receiving addresses. You should use this API to retrieve addresses (both Cold Receiving and Hot Sending) each time for a batch, and after that you should use V Device to verify the data of this batch.

        **Example response**::

            [
                {
                    "index": 0,
                    "address": "1B4qK6KTzWCnbNcx4WDYR99KfVRsU2zDcN"
                },
                {
                    "index": 1,
                    "address": "1Mzvo2UkBnEpQC8xkui23mYQQeL8NREqrJ"
                },
                {
                    "index": 2,
                    "address": "1n566cWbw6c3KLBJ8X1vvo8vi4G8BMmEV"
                },
                {"...": "..."},
                {
                    "index": 997,
                    "address": "1Hc6MffGiYPLJdwAnR42JpTYdGonfWEJ7N"
                },
                {
                    "index": 998,
                    "address": "1KqPMBXtmvKkLe9TCHzVR4New3c5xkVgge"
                },
                {
                    "index": 999,
                    "address": "1BN69Mnr48BDVgwXV7cKBBsCJ2iB6EHxUa"
                }
            ]

        **Parameters**:
            * ``batch_no`` *(required)* *(int)* - batch no.

        .. note:: batch no begins from 0, and each batch has 1,000 addresses (address index begins from 0 too).

Address History
---------------

    **GET /api/v1/open/address/history/** *(int: path)*

        Returns history addresses of certain path.

        **Example response**::

            [
                {
                    "index": 2,
                    "address": "1P4HA6XFs1j8S9FZtakhbCrT8JcZzWwH9h"
                },
                {
                    "index": 1,
                    "address": "1F1BnSuNwidFvmBmCHcqiWGePkzBfBTtgF"
                },
                {
                    "index": 0,
                    "address": "15qbwdkwUzUkk3PQ7HVSwJXJfNashY51S2"
                }
            ]

        **Parameters**:
            * ``path`` *(required)* *(int)* - path for receiving or change addresses.
            * ``since_address`` *(optional)* *(string)* - from which address to list.

        .. note::
            * ``path`` 0 means receiving addresses, and path 1 means change addresses.
            * ``since_address`` null represents that start from the beginning.

Address Next
------------

    **GET /api/v1/open/address/next**

        Returns next unused receiving address.

        **Example response**::

            {
                "index": 1,
                "address": "1Mzvo2UkBnEpQC8xkui23mYQQeL8NREqrJ"
            }

Tx List
-------

    **GET /api/v1/open/tx**

        Returns all related txs, and support pages.

        **Example response**::

            [
                {
                    "tx_hash": "d79deb9419b3cf62f08badef456a75396400bfe78cc38ed5ee6cbba27caf57e6", 
                    "confirmation": 3716, 
                    "confirm_at": "2016-08-04T12:32:27", 
                    "value": 500000, 
                    "tx_at": "2016-08-04T12:22:20", 
                    "inputs": [
                        {
                            "is_mine": false, 
                            "value": 620008, 
                            "prev_out_sn": 1, 
                            "sn": 0, 
                            "address": "1AdGeNK9aorEBmsgFtbu1ENZbPizxnHfeZ", 
                            "prev_tx_hash": "00ba3370e8c030e42cb43e9861d3d393dfa3e4e157c1ac2e8e5c5f69bda7e4c4"
                        }
                    ], 
                    "outputs": [
                        {
                            "status": 1, 
                            "is_mine": true, 
                            "sn": 0, 
                            "value": 500000, 
                            "address": "1BhtAhTmXu98JYQW9V4vvKAa6NJ1A7npJ1"
                        }, 
                        {
                            "status": 1, 
                            "is_mine": false, 
                            "sn": 1, 
                            "value": 100008, 
                            "address": "1KU9Vh4HzfYJMBo4QW3ytLdrd9bz6ghJSj"
                        }
                    ]
                }, 

                {
                    "tx_hash": "576aa53f24b2aaa12e35583caf7fe32f9de8569e440058b1468cb42b417cc48f", 
                    "confirmation": 3715, 
                    "confirm_at": "2016-08-04T12:37:07", 
                    "value": -110000, 
                    "tx_at": "2016-08-04T12:24:34", 
                    "inputs": [
                        {
                            "is_mine": true, 
                            "value": 500000, 
                            "prev_out_sn": 0, 
                            "sn": 0, 
                            "address": "1BhtAhTmXu98JYQW9V4vvKAa6NJ1A7npJ1", 
                            "prev_tx_hash": "d79deb9419b3cf62f08badef456a75396400bfe78cc38ed5ee6cbba27caf57e6"
                        }
                    ], 
                    "outputs": [
                        {
                            "status": 0, 
                            "is_mine": false, 
                            "sn": 0, 
                            "value": 100000, 
                            "address": "1Bitpie7nzdqcsHWYMVi4ePuY88hF2jr7E"
                        }, 
                        {
                            "status": 1, 
                            "is_mine": true, 
                            "sn": 1, 
                            "value": 390000, 
                            "address": "1M5CKnUywtfQBicDWFfbRQU7fVUACc71oT"
                        }
                    ]
                }, 

                {
                    "tx_hash": "f4f30ddf3379b30b49d1128989949e7e8d2754430fef56cb9e78e0d006371933", 
                    "confirmation": 3715, 
                    "confirm_at": "2016-08-04T12:37:07", 
                    "value": -110000, 
                    "tx_at": "2016-08-04T12:26:08", 
                    "inputs": [
                        {
                            "is_mine": true, 
                            "value": 390000, 
                            "prev_out_sn": 1, 
                            "sn": 0, 
                            "address": "1M5CKnUywtfQBicDWFfbRQU7fVUACc71oT", 
                            "prev_tx_hash": "576aa53f24b2aaa12e35583caf7fe32f9de8569e440058b1468cb42b417cc48f"
                        }
                    ], 
                    "outputs": [
                        {
                            "status": 0, 
                            "is_mine": false, 
                            "sn": 0, 
                            "value": 100000, 
                            "address": "1Bitpie7nzdqcsHWYMVi4ePuY88hF2jr7E"
                        }, 
                        {
                            "status": 1, 
                            "is_mine": true, 
                            "sn": 1, "value": 280000, 
                            "address": "13iUXsqRuuEXJGUtr9KKopsSnDpBQtqEQM"
                        }
                    ]
                }
            ]

        **Arguments**:
            * ``tx_hash`` *(optional)* *(str)* - from which tx_hash to retrieve txs.

        .. note:: txs are ordered by tx_time in desc. if tx_hash is not provided, it means to retrieve the latest 20 txs. if provided, then returns 20 txs since this tx_hash.

Tx Detail
---------

    **GET /api/v1/open/tx/detail/** *(str: tx_hash)*

        Returns tx details for specific tx.

        **Example response**::

            {
                "tx_hash": "1c56ac562ad216f3fe68e8142a7f28f4889886065cc77745af4c9ddaee17c6e1",
                "inputs": [
                    {
                        "is_mine": false,
                        "value": 2510000,
                        "prev_out_sn": 1,
                        "sn": 0,
                        "address": "19EbsdkWfihtQHn4CoN5Eoyzh7cqqPNSLR",
                        "prev_tx_hash": "6aac1207ced737dc5a576dc5812a1c38687a760e2e148e6e6b1f12c1bf121dc0"
                    }
                ],
                "confirmation": 908,
                "outputs": [
                    {
                        "status": 1,
                        "is_mine": true,
                        "sn": 0,
                        "value": 10000,
                        "address": "1B4qK6KTzWCnbNcx4WDYR99KfVRsU2zDcN"
                    },
                    {
                        "status": 1,
                        "is_mine": false,
                        "sn": 1,
                        "value": 2490000,
                        "address": "1BU1p3PU9MRcPrvggBmDEXokigZy5cxQso"
                    }
                ],
                "confirm_at": "2016-07-27T02:31:34",
                "value": 10000,
                "tx_at": "2016-07-27T02:21:53"
            }

        **Parameters**:
            * ``tx_hash`` *(required)* *(str)* - for which tx_hash to retrieve tx detail.
