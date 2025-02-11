## One time actions:

Download and install WAMP server (so you can run PHP scripts locally and don't have to trust me or another 3rd party with your password)

<http://sourceforge.net/projects/wampserver/>

Put the following files into the `...\wamp\www\` directory:

```
crawler.php
stats.php
colors.php
config.php
README.html
```

Startup the WAMP server (you don't have to put it online for this).
Leftclick the task bar icon. Click through PHP>PHP Extensions
Make sure that additional to the defaults the following extensions are enabled: `php_curl, php_tidy`

Edit the config file (`config.txt`);

## Every time actions:

1. Start your WAMP server
2. Go to "<http://127.0.0.1/crawler.php>" in your webbrowser (I coded for firefox and didn't check other browsers)
3. Wait for the data to be loaded.[<sup>1</sup>](#foot)
4. Once the data load script is done, click on the link at the end of the progress report to view your data.


## Notes

This script may stop working depending on changes of the Memrise webpage.

This script crawls the pages you have access to and as such can only analyse the data that is displayed. 
It cannot access the actual database behind the webpage.
So for example, if the page says that an item will be asked again "in about an hour",
the webpage will have a very specific point in time when it's going to ask it again,
but this script only has the "in about an hour" information.

Plants ready for harvesting may not show up in the graph.

> <sup id="foot">1</sup> Loading of all the data may take a while (the script is crawling through all the relevant pages),
> but progress should be displayed during loading.
> Whenever a "." shows up in the progress report that means that a page load timed out and the script is retrying.
> This is not very important, but if memrise or your connection is slow for some reason this might show up a lot.
> The time out is set at 5 seconds by default. So if you're seeing lots of dots and the script is never finishing,
> you might have to change that value in the config file.
