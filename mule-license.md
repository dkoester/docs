# To apply a new mule license

- MuleSoft makes available trial versions of its Enterprise Edition runtime for the purpose of evaluation. Though perfect for exploring the myriad uses of Mule, Anypoint Studio, and Mule Management Console, the trial license for Enterprise limits usage of the runtime. Complete the following steps to acquire and install an Enterprise license, then begin using Mule runtime in a production environment.

- Contact MuleSoft to acquire an Enterprise license in the form of a license.lic file.
[full instructions here](https://docs.mulesoft.com/mule-runtime/3.9/installing-an-enterprise-license)

###### shortened version
- backup key from 3.9.3/conf `muleLicenseKey.lic`
- stop mule
- delete that key from the folder
- put new folder in 3.9.3/bin
- run command `mule -installLicense ~/license.lic` where license.lic is the new license name
- should output valid key and put a new muleLicenseKey in the conf folder 
- mule start
- celebrate

###### full install

1. Before installing, it’s recommended to remove the previous License from your $MULE_HOME directory. To do so, navigate to $MULE_HOME/conf/ and delete the existing muleLicenseKey.lic file.

2. If you are installing your license on multiple platforms, back up your new license.lic file in another location before proceeding.

3. Make sure that the Mule Server is stopped (not running) and then open the terminal or command line on your system.

4. On Mac/Unix/Linux, from the $MULE_HOME/bin directory, run the following command:

`mule -installLicense ~/license.lic`

5. On Windows, first copy the license.lic file into the \bin folder, then execute the following in the command line:

`mule -installLicense license.lic `

6. In the $MULE_HOME/conf directory, Mule saves a new file called muleLicenseKey.lic. This shows that the license has been installed.

7. Start your Mule Server again, by the usual means.

