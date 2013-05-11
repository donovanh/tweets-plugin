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

### Prepare the HTML

Your Tweets output will need a container to be displayed. If you wish to use the attached CSS, add the following to your HTML first:

    <div class="tweets" id="tweet-container"></div>

The class <code>tweets</code> is used by the CSS to style the div. The id <code>tweet-container</code> is used by the plugin to identify where the tweets will be sent.

### Prepare the CSS

Download the [jquery.tweets.css](https://raw.github.com/donovanh/tweets-plugin/master/jquery.tweets.css) file and place it in your CSS folder. It can then be called in the <code>head</code> of your document like so:

    <link href="/stylesheets/jquery.tweets.css" media="screen, projection" rel="stylesheet" type="text/css" />

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

## Current version

0.1 - Gotta start somewhere

## Changelog

### 0.1
Initial code

## Pull requests

Pull requests are most welcome. If you have any questions, [send me an email](mailto:d@hop.ie) or [tweet @donovanh](http://twitter.com/donovanh).

## License

MIT License applies.

Copyright (c) 2013 Donovan Hutchinson

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
