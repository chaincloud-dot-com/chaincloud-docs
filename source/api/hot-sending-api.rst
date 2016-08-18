.. _hot-sending-api:

********************************************************************************
Hot Sending API
********************************************************************************

Hot Sending Tx Request
----------------------

    **POST /api/v1/open/tx/request**

        Post Hot Sending Tx Request.

        **Example response**::

            {
                "result": true
            }

        **Parameters**:
            * ``coin_code`` *(optional)* *(string)* - coin type, for example *(BTC)*.
            * ``user_tx_no`` *(required)* *(string)* - tx id in vweb.
            * ``outs`` *(required)* *(string)* - transfer to address and value.
            * ``vc_code`` *(required)* *(string)* - the sign of unsigntx.
            * ``is_dynamic_fee`` *(optional)* *(int)* - whether to charge the dynamic fee.
            * ``c_id`` *(required)* *(int)* - the channel id of sms to sign.

        .. note::
            * ``coin_code`` default *(BTC)*.
            * ``user_tx_no`` unique in vweb.
            * ``outs`` support multiple addresses.for example "1NbbvxBYxGGCBhaM8mow1HFWA7dB5yukmY,2000;1XaavxBYxGGCBhaM8mow1HFWA7dB5yukmY,3000";
            * ``is_dynamic_fee`` 0 no  1 yes  default 1.
            * ``vc_code`` and ``c_id`` is use to ensure security  .

Hot Sending Tx Detail
---------------------

    **GET /api/v1/open/tx/** *(int: user_tx_no)*

        Returns tx details for your specific tx_no.

        **Example response**::

            {
                "tx_hash": "897a7eb61ea4e9b5a72afa95573ccdc67d4edb3984509a11316664cb69a18065",
                "c_id": 2,
                "user_id": 40000,
                "send_request": {
                    "coin_code": "BTC",
                    "user_tx_no": "8",
                    "is_dynamic_fee": 1,
                    "outs": "1NbbvxBYxGGCBhaM8mow1HFWA7dB5yukmY,2000;1XaavxBYxGGCBhaM8mow1HFWA7dB5yukmY,3000"
                },
                "vc_code": "HxAK9Q4CdcKzypai9Wk4gjYwC8jeuHq9UWunAvyzRbO1a4PyZecmYF0WS5kdtBH80/0EtSETjurHyRctkCFsxVk=",
                "request_at": "2016-07-31T04:52:13",
                "hot_wallet_tx_id": 26,
                "tx_at": "2016-07-31T05:31:07",
                "hot_wallet_tx_status": 1
            }

        **Parameters**:
            * ``user_tx_no`` *(required)* *(int)* - for which user_tx_no to retrieve tx detail.

        .. note:: user_tx_no is the unique transaction id in your own system, you should use an auto incremented primary key as user_tx_no.
