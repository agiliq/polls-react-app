Deployment
====================

When using Webpack/create-react-app, you have a few options for deployment.

create-react-app comes with a build command that you can use to create a static bundle of the React app:
.. code-block:: bash
	$ cd client
	$ npm run build

This produces a build/ folder which you can serve with any static asset host. It contains all your app's HTML, JavaScript, and CSS files.

You can upload this folder to a host like S3 and deploy your app to AWS. Or, you can have the API server also serve your static assets. The GitHub repo of this app contains an example of the app prepared for deployment. 