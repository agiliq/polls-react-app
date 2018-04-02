Concurrently
================

Concurrently is a utility for running multiple processes. We'll see how it works by implementing it.

Make sure you're in the top-level directory and install it with npm:

.. code-block:: bash
	$ npm i --save-dev concurrently

We want concurrently to execute two commands, one to boot the API server and one to boot the Webpack development server. You boot multiple commands by passing them to concurrently in quotes like this:


.. code-block:: bash

	$ concurrently "command1" "command2"

If you were writing your app to just work on Mac or Unix machines, you could do something like this:

.. code-block:: bash

	$ concurrently "npm run server" "cd client && npm start"

Note the second command for booting the client first changes into the client directory and then runs npm start.

However, the && operator is not cross-platform (doesn't work on Windows). As such, we've included a start-client.js script with the project. This script will boot the client from the top-level directory in a manner that is cross-platform.

Ultimately, we'll want to boot concurrently like this:

.. code-block:: bash
	$ concurrently "npm run server" "npm run client"

This will be our start command. Let's add the start and client commands to our package.json now:

.. code-block:: json
	
	"scripts": {
    "start": "concurrently \"npm run server\" \"npm run client\"",
    "server": "node server.js",
    "client": "node start-client.js"
  },


For start, we execute both commands, escaping the quotes because we're in a JSON file. For client, we execute the start-client.js script with node.

Now we can boot both servers by running npm start.

With the foundations in place, let's wire the two up. We'll toss in the food lookup React components which will make requests against our API server.