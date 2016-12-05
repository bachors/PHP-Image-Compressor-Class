# PHP-Image-Compressor-Class
PHP library to compress images with a high level of compression without loosing the original quality.

<h2>Usage:</h2>
 

<pre>&lt;?php

// include ImgCompressor.php
include_once('lib/ImgCompressor.class.php');

// setting
$setting = array(
&nbsp; &nbsp;'directory' =&gt; 'compressed', // directory file compressed output
&nbsp; &nbsp;'file_type' =&gt; array( // file format allowed
&nbsp; &nbsp; &nbsp;'image/jpeg',
&nbsp; &nbsp; &nbsp;'image/png',
&nbsp; &nbsp; &nbsp;'image/gif'
&nbsp; &nbsp;)
);

// create object
$ImgCompressor = new ImgCompressor($setting);

// run('STRING original file path', 'output file type', INTEGER Compression level: from 0 (no compression) to 9);
// example level = 2 same quality 80%, level = 7 same quality 30% etc
$result = $ImgCompressor-&gt;run('original/world.png', 'jpg', 5); 

// result array
echo '&lt;pre&gt;';
print_r($result);
echo '&lt;/pre&gt;';</pre>
 <h2>Result:</h2>
 

<pre>Array
(
    [status] =&gt; success
    [data] =&gt; Array
        (
            [original] =&gt; Array
                (
                    [name] =&gt; world.png
                    [image] =&gt; original/world.png
                    [type] =&gt; image/png
                    [size] =&gt; 338915
                )

            [compressed] =&gt; Array
                (
                    [name] =&gt; 1480975672world.jpg
                    [image] =&gt; compressed/1480975672world.jpg
                    [type] =&gt; image/jpeg
                    [size] =&gt; 34318
                )

        )

)</pre>
 <h2>Error:</h2>
 

<pre>Array
(
    [status] =&gt; error
    [message] =&gt; ...

)</pre>
