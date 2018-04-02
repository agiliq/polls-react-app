react-scripts
===============

react-scripts is an NPM package specifically for use with create-react-app. It's the "black box" which contains the essentials:

Dependencies
++++++++++++++++

* Like Babel, ESLint, and Webpack.


Configuration
++++++++++++++++

* Config files for Webpack, Babel and ESLint, both for development and production.

Scripts
++++++++++

* For instance, the command react-scripts start runs a script shipped with this package. It's responsible for ultimately booting the Webpack development server.


To see it in action, we can run npm start from inside of this folder:

.. code-block:: bash

	$ cd client && npm start

This will launch a Webpack dev server and should also open localhost:3000 in your browser if you're on a Mac:

..image:: page.png

We have our API server in the top-level directory and we were able to boot that. And we have our client app down here in client and we're able to boot a server for this.

But why does our React app need its own server? And how are we going to get these two servers working together?

Understanding this requires getting down to The Rub.
