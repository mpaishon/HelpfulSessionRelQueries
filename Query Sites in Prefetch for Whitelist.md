# Enabling Debug Mode and Running Session Relevance in BigFix

## Step 1: Enable Debug Mode

To enable debug mode in your BigFix Console:
1. Press `CTRL + ALT + SHIFT + D`.

## Step 2: Run Session Relevance

Copy and paste the following session relevance into the presentation debugger or Web Reports QNA. 

**Note:** Make sure to update the site name in the query to match your specific use case.

```relevance
unique values of (matches (case insensitive regex "(http|https|ftp)://[^ ^/]*") of matches (case insensitive regex "^(download|prefetch).*$") of scripts of it) of actions whose (exists script of it) of fixlets of (bes sites; bes custom sites) whose (name of it = "Updates for Windows Applications")
```

## Example Output

This example shows the URLs found in the "Updates for Windows Applications" site:

```
http://airdownload.adobe.com
http://appldnld.apple.com
http://appldnld.apple.com.edgesuite.net
http://ardownload.adobe.com
http://download-akm.skype.com
http://download-installer.cdn.mozilla.net
http://download-origin.cdn.mozilla.net
http://download.adobe.com
http://download.cdn.mozilla.net
etc...
```

This output lists all the unique URLs found within the "Updates for Windows Applications" site that match the specified download or prefetch scripts.
