Mailbox Audit Log
=======
Mailbox audit logs are generated for each mailbox that has mailbox audit logging enabled. This tracks all user actions on any items in a mailbox.
Use **Get-MailboxAuditLog** to collect the mailbox audit log for a specific user or all user accounts.

Usage
""""""""""""""""""""""""""
Running the script without any parameters will gather the maibox audit logs for the last 90 days for all users:
::

   Get-MailboxAuditLog

Get mailbox audit log entries for the user HR[@]invictus-ir.com:
::

  Get-MailboxAuditLog -UserIds HR[@]invictus-ir.com

Get mailbox audit log entries for the users HR[@]invictus-ir.com and test[@]invictus-ir.com:
::

   Get-MailboxAuditLog -UserIds "test@invictus-ir.com,HR@invictus-ir.com"

Get mailbox audit log entries for the user test@invictus-ir.com between 2023/04/01 and 2023/04/04:
::

   Get-MailboxAuditLog -UserIds test[@]invictus-ir.com -StartDate 2023/04/01 -EndDate 2023/04/04

Parameters
""""""""""""""""""""""""""
-UserIds (optional)
    - UserIds is the UserIds parameter filtering the log entries by the account of the user who performed the actions.

-StartDate (optional)
    - StartDate is the parameter specifying the start date of the date range.
    - Default: Today -90 days

-EndDate (optional)
    - EndDate is the parameter specifying the end date of the date range.
    - Default: Now

Output
""""""""""""""""""""""""""
The output will be saved to the 'MailboxAuditLog' directory within the 'Output' directory, with the file name 'mailboxAuditLog_$($UserIds)_$($date).csv"'.
