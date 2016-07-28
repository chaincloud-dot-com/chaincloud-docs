.. _basic-api:

********************************************************************************
Basic API
********************************************************************************

All basic APIs.

Time
----
.. note::
    Only for a test!

.. http:get::  /api/v1/open/time/

    Get current server time.

   .. sourcecode:: js

      {
          "meta": {
              "limit": 20, 
              "next": "/api/v1/build/?limit=20&offset=20", 
              "offset": 0, 
              "previous": null, 
              "total_count": 86684
          }, 
          "objects": [BUILDS]
      }

   :>json integer limit: Number of Builds returned.
   :>json string next: URI for next set of Builds.
   :>json integer offset: Current offset used for pagination.
   :>json string previous: URI for previous set of Builds.
   :>json integer total_count: Total number of Builds.
   :>json array objects: Array of `Build`_ objects.


