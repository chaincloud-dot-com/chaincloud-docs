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
            }

Hot Sending Tx Detail
---------------------

    **GET /api/v1/open/tx/** *(int: user_tx_no)*

        Returns tx details for your specific tx_no.

        **Example response**::

            {
            }

        **Parameters**:
            * ``user_tx_no`` *(required)* *(int)* - for which user_tx_no to retrieve tx detail.

        .. note:: user_tx_no is the unique transaction id in your own system, you should use an auto incremented primary key as user_tx_no.

