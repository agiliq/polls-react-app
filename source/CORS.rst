CORS
=======

There’s one last step we need to do and that’s deal with Cross-Origin Resource Sharing (CORS). Whenever a client interacts with an API hosted on a different domain there are potential security issues. CORS requires the server to include specific HTTP headers that allow the browser to determine if and when cross-domain requests should be allowed.

The easiest way to handle this–and the one recommended by DRF–is to use middleware that will automatically include the appropriate HTTP headers based on our settings.

The recommended package is django-cors-headers which can be easily added to our existing project.

First quit our server Control+c and then install django-cors-headers with Pipenv.

.. code-block::bash

	$ pipenv install django-cors-headers

Then update our settings.py file in three places:

* add :code:`corsheaders` to the :code:`INSTALLED_APPS`
* add two new middlewares that need to appear at the top!
* create a :code:`CORS_ORIGIN_WHITELIST`

.. code-block::python

	INSTALLED_APPS = [
	    'django.contrib.admin',
	    'django.contrib.auth',
	    'django.contrib.contenttypes',
	    'django.contrib.sessions',
	    'django.contrib.messages',
	    'django.contrib.staticfiles',

	    'rest_framework',
	    'corsheaders', # new

	    'todos',
	]

	MIDDLEWARE = [
	    'corsheaders.middleware.CorsMiddleware', # new
	    'django.middleware.common.CommonMiddleware', # new
	    'django.middleware.security.SecurityMiddleware',
	    'django.contrib.sessions.middleware.SessionMiddleware',
	    'django.middleware.common.CommonMiddleware',
	    'django.middleware.csrf.CsrfViewMiddleware',
	    'django.contrib.auth.middleware.AuthenticationMiddleware',
	    'django.contrib.messages.middleware.MessageMiddleware',
	    'django.middleware.clickjacking.XFrameOptionsMiddleware',
	]

	CORS_ORIGIN_WHITELIST = (
	    'localhost:3000/'
	)

Note: We’re using the domain :code:`localhost:3000/` because that’s the default local port for React.

And that’s it! Now our backend is complete. Make sure the server is running.


.. code-block::bash
	$ python manage.py runserver




