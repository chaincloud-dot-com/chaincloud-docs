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

            {
            }

        **Parameters**:
            * ``batch_no`` *(required)* *(int)* - batch no.

        .. note:: batch no begins from 0, and each batch has 1,000 addresses (address index begins from 0 too).

Address History
---------------

    **GET /api/v1/open/address/history/** *(int: path)*

        Returns history addresses of certain path.

        **Example response**::

            {
            }

        **Parameters**:
            * ``path`` *(required)* *(int)* - path for receiving or change addresses.

        .. note:: path 0 means receiving addresses, and path 1 means change addresses.

Address Next
------------

    **GET /api/v1/open/address/next**

        Returns next unused receiving address.

        **Example response**::

            {
            }

Tx List
-------

    **GET /api/v1/open/tx**

        Returns all related txs, and support pages.

        **Example response**::

            {
            }

        **Arguments**:
            * ``tx_hash`` *(optional)* *(str)* - from which tx_hash to retrieve txs.

        .. note:: txs are ordered by tx_time in desc. if tx_hash is not provided, it means to retrieve the latest 20 txs. if provided, then returns 20 txs since this tx_hash.

Tx Detail
---------

    **GET /api/v1/open/tx/detail/** *(str: tx_hash)*

        Returns tx details for specific tx.

        **Example response**::

            {
            }

        **Parameters**:
            * ``tx_hash`` *(required)* *(str)* - for which tx_hash to retrieve tx detail.
