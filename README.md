PHP Console Progress Bar
========================

This class creates and maintains progress bars to be printed to the console. 
This file is a replica of the ezComponents console progress bar class (@link http://ezcomponents.org/docs/api/latest/ConsoleTools/ezcConsoleProgressbar.html)
allows a developer to just use the console progress bar features without the rest of the classes saving all the extra files and classes.

Example Usage:

```php
<?php

require_once('ConsoleProgressBar.php');

// initiate the class with the maximum value being 100
$progress = new ConsoleProgressBar(100);

// Start the progress bar before the actual actions are taken place
$progress->start();

// This is just an example that's why a simple look is being used
// in real world this can be a db record set process or any other long operation that is being
// done via the cli
for ($i = 0; $i <= 100; $i++) {

	// Do the actual processing here
	// .....
	// .....
	// .....

	// Advance one step by default
	// you can pass a second argument $step which will advance that number of steps
    $progress->advance();

    // For this example we will just sleep for a second
    sleep(1);
}

// Call finish at the end to make sure the bar goes to 100% if it didn't
$progress->finish();
echo "\n";
``

Available Options
=======================













