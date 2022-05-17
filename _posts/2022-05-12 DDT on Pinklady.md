---
title: 'DDT on pinklady'
date: 2022-05-22
permalink: /posts/2022/05/DDT on Pinklady/
tags:
  - cool posts
  - category1
  - category2
---
* To connect pinklady, the user should type "ssh libi292@pinklady.pnl.gov" in terminal.

I have installed the (master) development version of ATS on pinklady along with DDT as a debugger (the trial license is good through June 24). 
We must run the master branch as the linkage to PFLOTRAN actually runs (though I have yet to verify that it is correct). 
Please update all input decks to use it.

To run ats: 

* ssh to pinklady
* cd /software/hamm495
* (alt ats-master env_ats_master.sh lib)
* source env_ats_master.sh
* ![ssh_source](https://user-images.githubusercontent.com/21980320/168872974-dc36357d-c1b8-4bfb-a53e-b2b5b626aa13.png)


If you can not do source with an error source: not found. 
Please check the shell you used by env | grep SHELL.
Sometime, it will be sh not bash. Therefore, you need to swith sh to bash. or create a new file for sh.
chsh -s /bin/bash libi292 
which mpirun      
* ensure that the output from `which mpirun` prints "/software/hamm495/alt/bin/mpirun"
* navigate to the directory with the input file ats --xml_file=filename.xml

* Download ats-regression-tests-master.zip and unzip it on pinklady

To debug ats through DDT:

* Install VcXsrv (https://gcc02.safelinks.protection.outlook.com/?url=https%3A%2F%2Fsourceforge.net%2Fprojects%2Fvcxsrv%2F&amp;data=05%7C01%7Cbing.li%40pnnl.gov%7C3c5e1effa41c4fd8ce4708da3440c77b%7Cd6faa5f90ae240338c0130048a38deeb%7C0%7C0%7C637879750065872906%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&amp;sdata=8OdFdF%2BHpedsiULh0CvgDBv1Fa9tNEg1ot%2FDFIBxFRs%3D&amp;reserved=0) on your Window machine; Xming will not work) #Start the VcXsrv xserver # ssh to pinklady cd /software/hamm495 source env_ats_master.sh
which mpirun      
* ensure that the output from `which mpirun` prints "/software/hamm495/alt/bin/mpirun"
* navigate to the directory with the input file ddt & # Click on 'Run'
* Specify the location of the executable in the "Application" field (e.g. /software/hamm495/ats-master/amanzi-install-master-Debug/bin/ats)
* Specify the command line arguments in the "Arguments:" field (e.g. --xml_file=filename.xml) # Ensure that the checkbox to the left of Runtime is checked (this enables MPI) # Click Run

Please let me know if there are mistakes in these instructions or questions.  You must source the env_ats_master.sh file as it sets correct environment variables.
