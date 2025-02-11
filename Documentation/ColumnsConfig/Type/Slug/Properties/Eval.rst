.. include:: /Includes.rst.txt
.. _columns-slug-properties-eval:

====
eval
====

.. confval:: eval

   :type: string (list of keywords)
   :Scope: Proc. / Display

   Configuration of field evaluation.

   Keywords:

   unique
      Evaluate if a record is unique in the whole TYPO3 installation (specific to a language).
      This option is recommended as it allows to show any record stored inside other sites.
      The only downside is that it is not possible to have the same slug on multiple sites.

   uniqueInSite
      Requires the field to be unique for the current site and language. This allows for multiple records of the same table to have the same slug as long as these records are separated by their sites. Consequently records of a foreign site are not accessible with :php:`uniqueInsite` since slugs are looked up respecting the current site.

      .. warning::
           Be aware that using this option makes it impossible to show records stored inside other sites.
           If this is required, :php:`unique` should be used instead.

   uniqueInPid
      Requires the field to be unique for the current PID among other records on the same page.

   No other eval setting is checked for. It is possible to set different eval options, however it is
   recommended not to do so.

Examples
========

eval = uniqueInSite
-------------------

.. include:: /Images/Rst/Slug2.rst.txt

.. include:: /CodeSnippets/Slug2.rst.txt
