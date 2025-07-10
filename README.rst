================
historical-dates
================

django-historical-dates is a Django app to work with historical dates
and calendars in Django applications. A reusable Django app to handle
uncertain, partial, approximate, and ranged historical dates with
native `EDTF`_ (Extended Date/Time Format) support.

.. _EDTF: https://www.loc.gov/standards/datetime/

Detailed documentation is in the "docs" directory.

Features
-------

- Supports human-readable display dates
- Parses EDTF strings into sortable start and end dates
- Validates EDTF syntax on admin and forms
- Provides a `HistoricalDateField` for referencing in other models
- Handles various historic calendar systems

Quick start
-----------

1. Add "historical_dates" to your INSTALLED_APPS setting like this::

    INSTALLED_APPS = [
        ...,
        "historical_dates",
    ]

2. Run ``python manage.py migrate`` to create the models.

3. Use the historical dates in your models:

.. code-block:: python

   from historical_dates.fields import HistoricalDateField

   class Artifact(models.Model):
       production_date = HistoricalDateField()
