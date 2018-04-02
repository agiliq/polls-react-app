Tearing it down
===================
Let's shut down the app with CTRL+C and strip out everything but the server and see how we got here:

.. image:: startting-point.png

This removes the files inside client/.

The client folder is probably still hanging around. That's because the untracked node_modules folder is inside. Kill it:

.. image:: client.png