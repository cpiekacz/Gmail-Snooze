Gmail Snooze
============

Gmail Snooze is a [Google Apps Script](https://developers.google.com/apps-script/) which allows e-mail snoozing. It removes e-mails marked by one of the labels from inbox and bring them back later at a predefined time. It was inspired by the [Mailbox](http://www.mailboxapp.com) application for iPhone.

How to install
--------------

1. Login to your [Google Drive](http://drive.google.com)
2. Create a new script
3. Paste the code from the snooze.js file
4. Define your own labels and trigger hours in the [SETUP](#how-to-customize) section
5. Save the script
6. Click on 'Run > Install' in main menu, this will create labels in Gmail and define the following triggers:
	- cleanLabels - Time-driven - Minute timer - Every minute
	- runEvening - Time-driven - Day timer - 18:00 - 19:00
	- runTomorrow - Time-driven - Day timer - 6:00 - 7:00 (or earlier)
	- runSaturday - Time-driven - Week timer - Every saturday at 6:00 - 7:00
7. Authorize the script and grant access to Gmail

How to customize
----------------

You can change names of the labels as well as times at which events are fired. To do that just edit the coresponing parameters in the SETUP section of the script. You can also disable marking e-mail as unread after they are moved back into inbox. To do that just set the markUnread parameter to false.

``` js
var SETUP = {
	// Used to group all the snooze labels
	groupingLabel: 'Remind me',

	// Labels used for marking e-mails
	labels: {
		evening:  'In the evening',
		tomorrow: 'Tomorrow',
		saturday: 'On Saturday' 
	},
	
	// Hours at which triggers will be fired
	hours: {
		evening: 18, // In the evening at 6PM
		tomorrow: 6, // Tomorrow at 6AM
		saturday: 6  // On Saturday at 6AM
	},

	// Mark messages unread after moving them back into inbox
	markUnread: true
}
```

How to use
----------

When you want to snooze an email for one day, just mark it with label Tomorrow. After one minute it will be removed from your Inbox and marked as read. The next in the morning (at the time of you choosing), this script will bring this e-mail back to your inbox and mark it as unread.

Contact
-------

* cpiekacz@gmail.com
* https://twitter.com/cezex

Licence
-------

Gmail Snooze is available under the MIT license.

Copyright ? 2013 Cezary Piekacz

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.