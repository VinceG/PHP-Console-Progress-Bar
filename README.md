PHP Console Progress Bar
========================

This class creates and maintains progress bars to be printed to the console. 
This file is a replica of the ezComponents console progress bar class (@link http://ezcomponents.org/docs/api/latest/ConsoleTools/ezcConsoleProgressbar.html)
allows a developer to just use the console progress bar features without the rest of the classes saving all the extra files and classes.

Available Options
=======================

- barChar: Processed progress bar char (Default '=')
- emptyChar: Empty progress bar char (Default '-')
- formatString: Progress bar formatted line that actually displays the processed number, step count, total count, percentage etc.. (Default '%act% / %max% [%bar%] %fraction%%')
- fractionFormat: Progress bar fraction format (Default '%01.2f')
- progressChar: Progress bar progress leading char (Default '>')
- redrawFrequency: Redraw/Update the progress bar every X step(s) (Default: 1)
- step: Progress bar each advance call will advance X step(s) (Default: 1)
- width: Progress bar width (Default 100)
- actFormat: Progress bar current step format (Default '%.0f')
- maxFormat: Progress bar maximum step format (Default '%.0f')
- max: Progress bar maximum value (When it reaches 100%) (Default 100)

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
```