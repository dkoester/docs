# Mule Agent Upgrade

If you previously installed the agent with an earlier version of amc_setup, you can update the agent and retain your existing agent configuration in $MULE_HOME/conf/mule-agent.yml.
[full instructions here](https://docs.mulesoft.com/runtime-manager/installing-and-configuring-runtime-manager-agent)
#### PROD 

1. Block API traffic through firewall controll

#### To update an existing Runtime Manager agent:

1. Stop Mule or the API gateway runtime.

2. Extract the downloaded agent-setup-VERSION.zip file to $MULE_HOME/bin.

3. When prompted, overwrite any conflicting files.

4. Run `$MULE_HOME/bin/amc_setup -U.`

5. When you run amc_setup with the -U parameter, you can’t include other parameters on the command line.

6. Restart Mule or the API gateway runtime.

