PHP Console Progress Bar
========================

This class creates and maintains progress bars to be printed to the console. 
This file is a replica of the ezComponents console progress bar class (@link http://ezcomponents.org/docs/api/latest/ConsoleTools/ezcConsoleProgressbar.html)
allows a developer to just use the console progress bar features without the rest of the classes saving all the extra files and classes.

Example Usage:

```php
<?php

require_once('ConsoleProgressBar.php');


$progress = new ConsoleProgressBar(100);
$progress->start();

for ($i = 0; $i <= 100; $i++) {
    $progress->advance();
    sleep(1);
}

$progress->finish();
echo "\n";
```
