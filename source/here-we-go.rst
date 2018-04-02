Here we go
============

Ensure that you have create-react-app installed globally:

.. code-block:: bash

	$ npm i -g create-react-app

And then at the top-level directory of the project we'll create our client app. We want the React app to be in a folder called client, so we'll just use that name in the create-react-app command:

.. code-block:: bash

	$ create-react-app client

This creates a new directory with the following file structure:

..image:: filestructure.png


Taking a look at client/package.json, we note a single dev dependency:

..image:: package-json.png