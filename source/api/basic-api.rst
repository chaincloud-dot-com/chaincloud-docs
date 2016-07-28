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

Address
-------

    **GET /api/v1/open/address/batch** *(int: batch)*

        Returns a batch of receiving addresses.

        **Example response**::

            {
            }

        **Parameters**:
            * ``batch`` *(required)* *(int)* - batch no.

        .. note:: batch no begins from 0, and each batch has 1,000 addresses (address index begins from 0 too).


