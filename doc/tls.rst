TLS
===

Starting the EveBox Server with TLS
-----------------------------------

Before TLS can be used a private key and certificate must be obtained.

Enabling TLS on the Command Line
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. option:: --tls
   
   Enables TLS.

.. option:: --tls-cert FILE

   Specify the filename of the TLS certificate file.

.. option:: --tls-key FILE

   Specify the filename of the TLS private key. May be ommitted if the
   certificate file is a bundle containing the key.

Example::

  evebox --tls --tls-cert cert.pem --tls-key key.pem

Enabling TLS in the Configuration File
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

TLS can be enabled in the configuration file under ``http.tls``:

.. code-block:: yaml

   http:
     tls:
       enabled: true
       certificate: /path/to/cert.pem
       key: /path/to/key.pem

Creating a Self Signed Certificate and Key File
-----------------------------------------------

::

  openssl req -x509 -newkey rsa:4096 -keyout key.pem -out cert.pem -days 365 -nodes
