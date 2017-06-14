#application

The following operations can be performed on "application":


[import](#import-application) | [export](#export-application) | [rm](#rm-application)

##import application

Imports application configuration information from an AppExpert application template file. You can specify a deployment file along with the template file. A template file contains application and variable definitions. A deployment file contains information about the services, service groups, endpoints, and variables that were in the AppExpert application configuration at the time the template file was created.  Before you use template and deployment files, make sure that they are present in the /nsconfig/nstemplates/applications/ and /nsconfig/nstemplates/applications/deployment_files directories, respectively. You can transfer the files from your local drive to those directories on the NetScaler appliance by using either FTP or the NetScaler configuration utility. In the configuration utility, you can also import the files and create the application by using a single wizard (AppExpert > Applications > Import > AppExpert Template Wizard).


##Synopsys

import application &lt;apptemplateFilename> [-appname &lt;string>] [-deploymentFilename &lt;input_filename>]


##Arguments

<b>apptemplateFilename</b>
Name of the AppExpert application template file.

<b>appname</b>
Name to assign to the application on the NetScaler appliance. If you do not provide a name, the appliance assigns the application the name of the template file.

<b>deploymentFilename</b>
Name of the deployment file.



##Example

import app application sampleapp -apptemplatefilename sampleapp.xml -deploymentfilename deploy.xml

##export application

Exports application configuration information to an AppExpert application template file. A deployment file is created along with the template file. The template file contains application and variable definitions. The deployment file contains information about the services, service groups, endpoints, and variables that are in the AppExpert application configuration. The template and deployment files are exported to the /nsconfig/nstemplates/applications/ and /nsconfig/nstemplates/applications/deployment_files directories, respectively. If you use the configuration utility, you can also export an application to your local hard drive.


##Synopsys

export application &lt;appname> [-apptemplateFilename &lt;input_filename>] [-deploymentFilename &lt;input_filename>]


##Arguments

<b>appname</b>
Name of the AppExpert application whose configuration you want to export to a template file.

<b>apptemplateFilename</b>
Name with which to save the template file. If you do not specify a name, the template file is saved with the name of the application.

<b>deploymentFilename</b>
Name with which to save the deployment file. If you do not specify a name, a string consisting of an underscore and ?deployment? (_deployment) is automatically appended to the name of the template file to create the name of the deployment file.



##rm application

 Remove application configuration information from a netscaler device. You can specify an application name as input. All the configuration belonging to the specified application will be removed from the device.


##Synopsys

rm application &lt;appname>


##Arguments

<b>appname</b>
Name of the AppExpert application whose configuration you want to remove from the Netscaler appliance.



