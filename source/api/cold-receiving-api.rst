.. _cold-receiving-api:

********************************************************************************
Cold Receiving API
********************************************************************************

Address Txs
-----------

    **GET /api/v1/open/address/** *(str: address)* **/tx**

        Returns all txs for specific address.

        **Example response**::

            {
            }

        **Parameters**:
            * ``address`` *(required)* *(str)* - specific address.

        .. note:: You can use this API to monitoring all your Cold Receiving addresses.

