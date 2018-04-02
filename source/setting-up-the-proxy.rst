Setting up the proxy
==========================

To have the Webpack development server proxy our API requests to our API server, we just need to add the following line to client/package.json:

.. code-block:: python

	// Inside client/package.json
	"proxy": "http://localhost:3001/",

We're set.