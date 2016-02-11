Nagios or Icinga Plugin for Alfresco - Toni de la Fuente (blyx.com)

Original and based on Nagios JMX Plugin of Felix Roethenbacher (Copyright 2009)

*NAGIOS PLUGIN FOR ALFRESCO*

31/Jan/2010
Version 1.0 - first release (Suport Alfresco Enterprise 3.2 and above)

2/Feb/2010
Version 1.1 - added performance data to graph jmx checks (thanks Cesar Capillas - zylk.net)

13/Nov/2012
Version 1.2 - added SOLR checks and workflow information (Activiti/JBPM) tested with Alfresco Enterprise 4.1.1

30/Aug/2013
Version 1.3 - updated check_jmx (renamed as check_alfresco), now when critical is less than warning the threshold is treated as values less than. Also this version has -u and -p parameters and the command script changes. If you are monitoring Alfresco in WebSphere, use "check_alfresco_old" for SystemLoadAverage. Thanks to Colin Stephenson (Armedia) for this.

3/Sep/2013
Version 1.3.1 - fixed the check_alfresco script.

Change your JMX credentials in Alfresco: (for persistent change see here http://docs.alfresco.com/5.0/tasks/jmx-access.html)

For quick test:
TOMCAT_PATH/webapps/alfresco/WEB-INF/classes/alfresco/alfresco-jmxrmi.access

monitorRole   readonly
 #controlRole   readwrite

TOMCAT_PATH/webapps/alfresco/WEB-INF/classes/alfresco/alfresco-jmxrmi.password

monitorRole  newpassword
 # controlRole  change_asap

INSTALLATION

Copy next two files to your Nagios plugin directory.

  - check_alfresco
  - check_alfresco.jar
  
For a couple of sample command definitions copy:

  - alfresco-commands.cfg
  
to your Nagios plugin configuration directory or add this command definitions to your commands.cfg file, otherwise add next lines to nagios.cfg file:

# Definitions for monitoring Alfresco Enterprise
cfg_file=/usr/local/icinga/etc/objects/alfresco-commands.cfg
cfg_file=/usr/local/icinga/etc/objects/alfresco-server.cfg

Edit alfresco-server.cfg to fits your needs in terms of alerts threshold for warning and critical
Edit last 3 commands in alfresco-commands.cfg to set your Repository Path

In order to use command definitions you can use something like next line in your "define service" for each host (USERNAME and PASSWORD are jmxrmi configured credentials):

  - check_alfresco_HeapMemoryUsage_Used!PORT!USERNAME!PASSWORD!750000000!800000000

Copy alfresco.gif logo to your Nagios/Icinga logos directory ($NAGIOS_PATH/share/images/logos)


