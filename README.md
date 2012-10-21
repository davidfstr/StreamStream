# StreamStream

A stream wrapper implementation that reads from another underlying stream.
 
This is useful to pass a stream as an input to a PHP API that only accepts
URIs for its inputs, such as [XMLReader].

[XMLReader]: http://php.net/manual/en/book.xmlreader.php

## Example

```
require_once 'StreamStream.php'

// Open a stream
$stream = fopen('http://en.blog.wordpress.com/feed/', 'rb');

// Create a URI for the stream
$streamUri = StreamStream::createUriForStream($stream);

// Pass the URI to another API
$xmlReader = new XMLReader();
$xmlReader->open($streamUri);
```

## Requirements

* PHP 5.2.11 or later

## License

This code is licensed under the Apache License 2.0. Details can be found in the file [LICENSE.txt].

[LICENSE.txt]: https://github.com/davidfstr/StreamStream/blob/master/LICENSE.txt
