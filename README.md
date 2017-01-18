## What is MsgKit?

MsgKit is a 100% managed C# .NET library (no PINVOKE or whatsoever) which may be used for the creation and parsing (in the near future) of messages (E-Mail, Appointments, Journals and Stickey Notes) that are Outlook compatible

## History

- Started in 2015
- Picked up again in August 2016, adding all the know MAPI (Named) properties
- Finished adding all the named properties

## License Information

MsgKit is Copyright (C) 2015-2017 Magic-Sessions and is licensed under the MIT license:

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in
    all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
    THE SOFTWARE.

## Installing via NuGet

At the moment there is no package on NuGet... there will be one when the code is stable.
The code is working but don't blame me when you find some bugs or un-finished methods (it is a lot of work to make a library that "just" makes MSG files)

### Creating an Outlook Message file

```csharp
var email = new Email(
	new Sender("peterpan@neverland.com", "Peter Pan"),
	new Representing("tinkerbell@neverland.com", "Tinkerbell"), 
	"Hello Neverland subject");
					  
email.Recipients.AddTo("captainhook@neverland.com", "Captain Hook");
email.Recipients.AddCc("crocodile@neverland.com", "The evil ticking crocodile");
email.Subject = "This is the subject";
email.BodyText = "Hello Neverland text";
email.BodyHtml = "<html><head></head><body><b>Hello Neverland html</b></body></html>";
email.Importance = MessageImportance.IMPORTANCE_HIGH;
email.IconIndex = MessageIconIndex.ReadMail;
email.Attachments.Add(@"d:\crocodile.jpg");
email.Save(@"c:\test.msg");

// Show the message
System.Diagnostics.Process.Start(@"c:\test.msg");
```
Core Team
=========
    Sicos1977 (Kees van Spelde)

Support
=======
If you like my work then please consider a donation as a thank you.

<a href="https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=NS92EXB2RDPYA" target="_blank"><img src="https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif" /></a>

## Reporting Bugs

Have a bug or a feature request? [Please open a new issue](https://github.com/Sicos1977/MsgKit/issues).

Before opening a new issue, please search for existing issues to avoid submitting duplicates.
