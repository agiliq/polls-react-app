How to get "react-app" to work with your API
===============================================

In this post, we detail how to use the create-react-app project along with an API server.

Anyone who tells you that React is easy to get started with isn't lying. You can drop React into your production application, today. All you have to do is include React and ReactDOM in some script tags:

.. code-block:: html
	<script src='https://cdnjs.cloudflare.com/ajax/libs/react/15.2.1/react.min.js'></script>
	<script src='https://cdnjs.cloudflare.com/ajax/libs/react/15.2.1/react-dom.min.js'></script>

However, if you're like most developers, you will be quickly lured away from these tranquil waters. JSX, ES6, ES6 modules, hot reloading — pick your bait.

While there are discrete steps you can take to enable individual advantages, you'll hit limitations with each sooner or later. For example, you can load babel in script tags and get JSX and ES6. But you'll start running into problems when you want to break up your app across files and use the ES6 module pattern or roll out browser-less unit tests.

Sure, not all roads lead to a JavaScript bundler. But developers starting out have many compelling reasons to want to use one. A well-configured environment gives you the ability to use the complete ES6 feature set as well as other bells and whistles like hot reloading.



