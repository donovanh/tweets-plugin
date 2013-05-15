# Tweets Plugin

This is a jQuery plugin for use with the [Tweets Node.js app](http://github.com/donovanh/tweets).

## Usage

This plugin requires a server-side component. It it designed to work with the [Tweets Node.js app](http://github.com/donovanh/tweets), as it relies on the presence of JSON data from the server. Ensure the server-side component is in place **before** setting up the jQuery plugin.

### Set up the JS

This plugin requires jQuery and Handlebars. They can be called in from a CDN:

    <script src="http://code.jquery.com/jquery-2.0.0.min.js"></script>
    <script src="http://cdnjs.cloudflare.com/ajax/libs/handlebars.js/1.0.0-rc.3/handlebars.min.js"></script>

Download the [jquery.tweets.js](https://raw.github.com/donovanh/tweets-plugin/master/jquery.tweets.js) file and place it in your JavaScript folder. It would then be included something like this:

    <script src="/javascripts/jquery.tweets.js"></script>

To make use of the Socket.io functionality, it is necessary to connect to your Tweets server. This downloads the Socket.io client side code automatically. Replace "YOUR_URL" with the URL of your Tweets server and add this script tag:

    <script src="http://YOUR_URL/socket.io/socket.io.js"></script>

### Prepare the HTML

Your Tweets output will need a container to be displayed. If you wish to use the attached CSS, add the following to your HTML first:

    <div class="tweets" id="tweet-container"></div>

The class <code>tweets</code> is used by the CSS to style the div. The id <code>tweet-container</code> is used by the plugin to identify where the tweets will be sent.

### Prepare the CSS

Download the [jquery.tweets.css](https://raw.github.com/donovanh/tweets-plugin/master/jquery.tweets.css) file and place it in your CSS folder. It can then be called in the <code>head</code> of your document like so:

    <link href="/stylesheets/jquery.tweets.css" media="screen, projection" rel="stylesheet" type="text/css" />

The **SASS** folder contains the SASS equivalent if you prefer your CSS pre-processed.

### Call the plugin in JS

The plugin can be initialised as following:

    <script>
      /* Initialise the Tweets plugin */
      $.tweets({
        searchPhrase: 'hop.ie',
        templateID: '',
        destinationID: 'tweet-container',
        tweetSource: 'http://YOUR-SERVER-URL'
      });
    </script>

Make sure and replace <code>searchPhrase</code> with a search relevant to your results. This can be a username (@username), a URL (example.com) or anything you'd use to search Twitter.

Replace the <code>tweetSource</code> with the URL of your Node.js app. If testing locally, this would be <code>http://localhost:5000</code>

### Creating your own template

Since this plugin uses Handlebars for the templating, you can specify your own template. Here's one to start with:

    <script type="text/x-handlebars-template" id="tweet-template">
      <article class="tweet">
        <section class="user-details">
          <a href="http://twitter.com/{{from_user}}">
            <div class="user-image" style="background-image: url({{profile_image_url}})"></div>
            <p>
              <strong>{{from_user_name}}</strong>
              <span>{{from_user}}</span>
            </p>
          </a>
        </section>
        <p class="text">{{{text}}}</p>
        <p class="timing"><a href="http://twitter.com/{{from_user}}/statuses/{{id_str}}">{{created_at}}</a></p>
      </article>
    </script>

Specify the <code>templateID</code> in the above JavaScript to use your template in the views.

## Current version

0.2 - Streamin'

## Changelog

### 0.2
Adding some streaming functionality. Documentation to follow.

### 0.1
Initial code

## Pull requests

Pull requests are most welcome. If you have any questions, [send me an email](mailto:d@hop.ie) or [tweet @donovanh](http://twitter.com/donovanh).

## License

MIT
