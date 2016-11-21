.. _cold-receiving-api:

********************************************************************************
Cold Receiving API
********************************************************************************

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

        .. note:: txs are ordered by tx_time in asc. if tx_hash is not provided, it means to retrieve the earlist 20 txs. if provided, then returns 20 txs since this tx_hash. The is_mine field in inputs and outputs list should be used to determine whether this input's or output's address belongs to the user.
