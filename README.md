Laravel4 Minify Package
===============

A Laravel 4 package for minifying your .css and .js. It caches the file with an uniq fingerprint. When you adjust your CSS/JS, your old cached/minified files are deleted, and a new cachefile is placed.


<h3>Installation</h3>
Instal it via composer

Add the following line in your composer.json
<pre>
  "ceesvanegmond/minify": "dev-master"
</pre>
Please add the following line in your config/app.php
<pre>
  	'CeesVanEgmond\Minify\MinifyServiceProvider',
</pre>

<h3>Config</h3>
You can publish the config file, or you can edit it directly. There are several options.
<pre>
'css_path' => The CSS path (from your public) defaults to '/css/'
'css_build_path' => The build path where the minified + concatenate build files are (relative from above aption) defaults to 'builds/'
'js_path' => The JS path (from your public) defaults to '/js/'
'js_build_path' => The build path where the minified + concatenate build files are (relative from above aption) defaults to 'builds/'
</pre>

That's it, you can now start using the package

<h3>Usage</h3>
There are two helpers available to use, the 'stylesheet' helper, and the 'javascript' helper
Example to minify your JavaScript (in .blade file)

<pre>
{{ javascript(array(
  	'jquery-1.9.1.min.js',
		'hashchange.js',
		'tracer.js',
		'includes.js',
		'lightbox.js',
		'history.js',
		'transforms.js',
		'main.js',
		'ga.js'
	)) 
}}
</pre>

Or CSS 

<pre>
{{ stylesheet(array('main.css', 'main.blade')) }}
</pre>

Note!, For main.blade to work you need to have a main.blade.php file in views/CSS/.

You'll notice that you can set multiple files as an array, or just one file (string)
The system will only react if you're' not on the 'local' environment!!!

