The app's React components
==============================

Let's steal the React source files from the master branch. This will save you from some copying & pasting:

.. code-block:: bash
	$ git checkout master -- {client/src,client/semantic,client/semantic.json}

We use Semantic UI for styling the app, which we copy over as well. It's loaded inside of src/index.js. index.css contains a few kludgey margins.

For brevity, we won't walk through the React components. For the purposes of reading along, you just need to know that changing the value of the search bar (the FoodSearch component) ultimately calls search() on Client.

Client.js contains a Fetch call to our API endpoint:

.. code-block:: javascript

	function search(query) {
	  return fetch(`/api/food?q=${query}`, {
	    accept: 'application/json',
	  }).then(checkStatus)
	    .then(parseJSON);
	}
This is the one touch point between our React web app and the API server.

Notice how the URL does not include the base localhost:3001. That's because, as noted earlier, we want this request to be made to the Webpack development server. Thanks to the configuration established by create-react-app, the Webpack dev server will infer what traffic to proxy. It will proxy a request if the URL is not recognized or if the request is not loading static assets (like HTML/CSS/JS).

We just need to instruct Webpack to use the proxy.