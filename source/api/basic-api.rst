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
            }

Address Batch
-------------

    **GET /api/v1/open/address/batch/** *(int: batch_no)*

        Returns a batch of receiving addresses.

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


