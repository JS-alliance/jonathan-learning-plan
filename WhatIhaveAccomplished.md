What I have accomplished
========================

Fixing the problem and sending an alert
----------------------------------------

When the manager complained about not being able to fix the issue at a venue, I created a script that would fix the issue, copy the state of the software, notify the tech of the incident, and upload the state of the software to dropbox and link the technician.

    @echo off

    taskkill /im python.exe

    For /f "tokens=2-4 delims=/ " %%a in ('date /t') do (set mydate=%%c-%%a-%%b)
    For /f "tokens=1-2 delims=/:" %%a in ("%TIME%") do (set mytime=%%a%%b)

    echo d | XCOPY "C:\Gatekeeper" "C:\Users\synertia\Dropbox\Gatekeeper-Incidents\Gatekeeper-incident-%mydate%_%mytime%" /E

    for /R C:\Gatekeeper\ftp %%f in (*.jpg) do move "%%f" C:\Gatekeeper\tmp\0001\B\DCIM\100EOS7D\

    start C:\Gatekeeper\gatekeeper.bat

    set SERVER=127.0.0.1:1099
    set USER=mmtech.notifications@gmail.com
    set PW=N0t1fyM3
    set FROMNAME=mmtech.notifications@gmail.com
    set TO=jonathan.lewis@magicmemories.com
    set CC=4157947109@txt.att.net
    set SUBJECT="Gatekeeper incident at Branson Belle"
    set BODY="Gatekeeper has been restarted at the Showboat Branson Belle.  A copy of the state of Gatekeeper Gatekeeper-incident-%mydate%_%mytime% is available from the included Dropbox link https://www.dropbox.com/sh/smtgcwo66g1lyyt/AABBUlEHvtY3DaQ4gCDWbo66a?dl=0.  This is an automatically generated message."
    blat -server %SERVER% -f %FROMNAME% -u %USER% -pw %PW% -to %TO% -cc %CC% -subject %SUBJECT% -body %BODY% -log log.txt -debug
