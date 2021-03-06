This LabVIEW project "CS++.lvproj" is used to develop the successor of the CS Framework and is based on LVOOP and the Actor Framework.

- CS++ will be based on native LabVIEW classes and the Actor Framework.
- CS++ will follow the KISS principle: "Keep It Smart & Simple"

The project GIT workflow contains four branches: 
- Preview: new ideas and prototypes
- MainDev: main development line
- RC: release candidates
- master: released versions

Currently used development SW is LabVIEW 2015 SP1

Project is in pre-alpha state, so the most active branch at the moment is MainDev.

Related documents and information
=================================
- README.txt
- Release_Notes.txt
- EUPL v.1.1 - Lizenz.pdf
- Contact: H.Brand@gsi.de or D.Neidherr@gsi.de
- Download, bug reports... : http://github.com/HB-GSI/CSPP
- Documentation:
  - Refer to Documantation Folder 
  - NI Actor Framework: https://decibel.ni.com/content/groups/actor-framework-2011?view=overview
  - CS Framework: http://wiki.gsi.de/cgi-bin/view/CSframework/WebHome

GIT Submodules
==============
- Packages/CSPP_Core: This package is used as submodule.
- Packages/CSPP_ObjectManager: This package is used as submodule.

Run to pull:
  - git submodule init
  - git submodule update

Optional submodules
-------------------
- Packages/CSPP_DeviceBase: Definition of CS++Device ancestor classes
- Packages/CSPP_IVI: Implementations of derived CS++Device classes using IVI driver
- Packages/CSPP_DSC: Containing DSC Alarm- & Trend-Viewer
- Packages/CSPP_DIM: Providing DIM for PV communication
- Packages/CSPP_Syslog: Providing a Syslog based Message Handler 
- Packages/CSPP_Examples: Illustrating the usage of the above packages

Optional External Dependencies
=================================
- Syslog; Refer to http://sine.ni.com/nips/cds/view/p/lang/de/nid/209116
- Monitored Actor; Refer to https://decibel.ni.com/content/thread/18301 and http://lavag.org/topic/17056-monitoring-actors

Getting started:
=================================
- Clone this repository, if not alread done.
- Switch to the desired branch.
- Get submodules:
  - git submodule init
  - git submodule update
- Create a hard link to the custom error file(s): 
  - cd <LabVIEW 2015>\user.lib\errors
  - mklink /h CS++Core-errors.txt Packages\CSPP_Core\CS++Core-errors.txt
- Create a project specific copy of "CS++.lvproj" ( or "CS++-Linux.lvproj") 
  - or add CS++CoreContent.vi into your own LabVIEW project. You can drag the desired libraries from the dependencies into your virtual project folder structure.
- You need to create your project specific CS++.ini-file, like "CSPP_Core.ini" containing samples of all classes and actors, etc.
- You need to create and deploy your project specific shared Variable libraries.
  - Sample shared variable libraries should be available on disk in the corresponding package folder.
  - If you plan to used process variables on Linux, you need to configure the DataSocket-Server on a Window-PC first. 
- Run your project specific "CS++Main.vi"
  - Concatenate the desired Content.vi's, at least _CS++CoreContent.vi_ or _CS++CoreContent-Linux.vi_ , to the _Launch CS++StartActor.vi_ before execution.

Author: H.Brand@gsi.de, D.Neidherr@gsi.de

Copyright 2013  GSI Helmholtzzentrum f�r Schwerionenforschung GmbH

Planckstr.1, 64291 Darmstadt, Germany

Lizenziert unter der EUPL, Version 1.1 oder - sobald diese von der Europ�ischen Kommission genehmigt wurden - Folgeversionen der EUPL ("Lizenz"); Sie d�rfen dieses Werk ausschlie�lich gem�� dieser Lizenz nutzen.

Eine Kopie der Lizenz finden Sie hier: http://www.osor.eu/eupl

Sofern nicht durch anwendbare Rechtsvorschriften gefordert oder in schriftlicher Form vereinbart, wird die unter der Lizenz verbreitete Software "so wie sie ist", OHNE JEGLICHE GEW�HRLEISTUNG ODER BEDINGUNGEN - ausdr�cklich oder stillschweigend - verbreitet.

Die sprachspezifischen Genehmigungen und Beschr�nkungen unter der Lizenz sind dem Lizenztext zu entnehmen.