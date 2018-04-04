# xhprof-html

xhprof (or tideways) visualize html tool from [xhprof repo](https://github.com/phacility/xhprof).


## Usage

1. clone repo
2. ```$ php -S localhost:8000```
3. Access http://localhost:8000/?dir={Your xhprof profiling result dir}


## Tideways example

1. Install [tideways extension](https://github.com/tideways/php-xhprof-extension)
2. Write code and save profiler result.

```
<?php

tideways_xhprof_enable();

my_application();

$data = tideways_xhprof_disable();

$filename = '/tmp/' . intval(microtime(true)) . mt_rand(1,10000) . '.xhprof';
file_put_contents($filename, serialize($data));
echo 'Profile Result: ' . $filename;
```

3. Start this web app at PHP build-in server.

```
$ php -S localhost:8000
```

4. Access http://localhost:8000/?dir=/tmp

5. Enjoy profiling!
