This package contains a Nagios/Icinga Java plugin to check via JMX values to Alfresco Enterprise 3.2 and above. It contains 39 checks and supports performance data to graph results of checks with pnp4nagios. More information: http://blyx.com

31/Jan/2010 Version 1.0 - first release (Suport Alfresco Enterprise 3.2 and above)

2/Feb/2010 Version 1.1 - added performance data to graph jmx checks (thanks Cesar Capillas - zylk.net)

13/Nov/2012 Version 1.2 - added SOLR checks and workflow information (Activiti/JBPM) tested with Alfresco Enterprise 4.1.1

30/Aug/2013 Version 1.3 - updated check_jmx (renamed as check_alfresco), now when critical is less than warning the threshold is treated as values less than. Also this version has -u and -p parameters and the command script changes. If you are monitoring Alfresco in WebSphere, use "check_alfresco_old" for SystemLoadAverage. Thanks to Colin Stephenson (Armedia) for this.
