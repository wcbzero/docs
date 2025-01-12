---
title: Manage NetQ Agents
author: Cumulus Networks
weight: 49
aliases:
 - /display/NETQ21/Manage+NetQ+Agents
 - /pages/viewpage.action?pageId=12321061
pageID: 12321061
product: Cumulus NetQ
version: '2.1'
imgData: cumulus-netq-21
siteSlug: cumulus-netq-21
---
At various points in time, you might want to change which network nodes
are being monitored by NetQ or look more closely at a network node for
troubleshooting purposes. Adding the NetQ Agent to a switch or host is
described in [Install
NetQ](/version/cumulus-netq-21/Cumulus-NetQ-Deployment-Guide/Install-NetQ).
Disabling an Agent is described here and managing NetQ Agent logging is
also presented.

## Modify the Configuration of the NetQ Agent on a Node

The agent configuration commands enable
you to add and remove agents from switches and hosts, start and stop
agent operations, add and remove Kubernetes container monitoring, add or
remove sensors, debug the agent, and add or remove FRR (FRRouting).

{{%notice info%}}

Commands apply to one agent at a time,
and are run from the switch or host where the NetQ Agent resides.

{{%/notice%}}

The agent configuration commands include:

    netq config add agent frr-monitor [<text-frr-docker-name>]
    netq config add agent kubernetes-monitor [poll-period <text-duration-period>]
    netq config add agent loglevel [debug|error|info|warning]
    netq config add agent sensors
    netq config add agent server <text-opta-ip> [port <text-opta-port>] [vrf <text-vrf-name>]
    netq config (start|stop|status|restart) agent
    netq config del agent (agent-url|frr-monitor|kubernetes-monitor|loglevel|sensors|server)
    netq config show agent [frr-monitor|kubernetes-monitor|loglevel|sensors] [json]

This example shows how to specify the IP address and optionally a
specific port on the NetQ Platform where agents should send their data.

    cumulus@switch~:$ netq config add agent server 10.0.0.23

This example shows how to configure the agent to send sensor data.

    cumulus@switch~:$ netq config add agent sensors

This example shows how to start monitoring with Kubernetes.

    cumulus@switch:~$ netq config add kubernetes-monitor

{{%notice info%}}

After making configuration changes to your agents, you must restart the
agent for the changes to take effect. Use the `netq config restart
agent` command.

{{%/notice%}}

## Disable the NetQ Agent on a Node

You can temporarily disable NetQ Agent on a node. Disabling the agent
maintains the activity history in the NetQ database.

To disable NetQ Agent on a node, run the following command from the
node:

    cumulus@switch:~$ netq config stop agent

## Remove the NetQ Agent from a Node

You can decommission a NetQ Agent on a given node. You might need to do
this when you:

  - RMA the switch or host being monitored
  - Change the hostname of the switch or host being monitored
  - Move the switch or host being monitored from one data center to
    another

{{%notice note%}}

Decommissioning the node removes the agent server settings from the
local configuration file.

{{%/notice%}}

To decommission a node from the NetQ database:

1.  On the given node, stop and disable the NetQ Agent service.

        cumulus@switch:~$ sudo systemctl stop netq-agent
        cumulus@switch:~$ sudo systemctl disable netq-agent

2.  On the NetQ Appliance or Platform, decommission the node.

        cumulus@netq-appliance:~$ netq decommission <hostname>

## Configure Logging for a NetQ Agent

The logging level used for a NetQ Agent determines what types of events
are logged about the NetQ Agent on the switch or host.

First, you need to decide what level of
logging you want to configure. You can configure the logging level to be
the same for every NetQ Agent, or selectively increase or decrease the
logging level for a NetQ Agent on a problematic node.

| Logging Level | Description |
| ------------- | ----------- |
| debug         | Sends notifications for all debugging-related, informational, warning, and error messages. |
| info          | Sends notifications for informational, warning, and error messages (default). |
| warning       | Sends notifications for warning and error messages. |
| error         | Sends notifications for errors messages. |

You can view the NetQ Agent log directly. Messages have the following
structure:

`<timestamp> <node> <service>[PID]: <level>: <message>`

| Element         | Description                                                                                  |
| --------------- | -------------------------------------------------------------------------------------------- |
| timestamp       | Date and time event occurred in UTC format                                                   |
| node            | Hostname of network node where event occurred                                                |
| service \[PID\] | Service and Process IDentifier that generated the event                                      |
| level           | Logging level in which the given event is classified; *debug*, *error*, *info*, or *warning* |
| message         | Text description of event, including the node where the event occurred                       |

For example:

{{% imgOld 0 %}}

This example shows a portion of a NetQ Agent log with debug level
logging.

    ...
    2019-02-16T18:45:53.951124+00:00 spine-1 netq-agent[8600]: INFO: OPTA Discovery exhibit url hydra-09.cumulusnetworks.com port 4786
    2019-02-16T18:45:53.952035+00:00 spine-1 netq-agent[8600]: INFO: OPTA Discovery Agent ID spine-1
    2019-02-16T18:45:53.960152+00:00 spine-1 netq-agent[8600]: INFO: Received Discovery Response 0
    2019-02-16T18:46:54.054160+00:00 spine-1 netq-agent[8600]: INFO: OPTA Discovery exhibit url hydra-09.cumulusnetworks.com port 4786
    2019-02-16T18:46:54.054509+00:00 spine-1 netq-agent[8600]: INFO: OPTA Discovery Agent ID spine-1
    2019-02-16T18:46:54.057273+00:00 spine-1 netq-agent[8600]: INFO: Received Discovery Response 0
    2019-02-16T18:47:54.157985+00:00 spine-1 netq-agent[8600]: INFO: OPTA Discovery exhibit url hydra-09.cumulusnetworks.com port 4786
    2019-02-16T18:47:54.158857+00:00 spine-1 netq-agent[8600]: INFO: OPTA Discovery Agent ID spine-1
    2019-02-16T18:47:54.171170+00:00 spine-1 netq-agent[8600]: INFO: Received Discovery Response 0
    2019-02-16T18:48:54.260903+00:00 spine-1 netq-agent[8600]: INFO: OPTA Discovery exhibit url hydra-09.cumulusnetworks.com port 4786
    ...

**Example: Configure debug-level logging**

1.  Set the logging level to *debug.*

        cumulus@switch:~$ netq config add agent loglevel debug

2.  Restart the NetQ Agent.

        cumulus@switch:~$ netq config restart agent

3.  Optionally, verify connection to the NetQ platform by viewing the
    `netq-agent.log` messages.

**Example: Configure warning-level logging**

    cumulus@switch:~$ netq config add agent loglevel warning
    cumulus@switch:~$ netq config restart agent

**Example: Disable Agent Logging**

If you have set the logging level to
*debug* for troubleshooting, it is recommended that you either change
the logging level to a less heavy mode or completely disable agent
logging altogether when you are finished troubleshooting.

To change the logging level, run the
following command and restart the agent service:

    cumulus@switch:~$ netq config add agent loglevel <LOG_LEVEL> 
    cumulus@switch:~$ netq config restart agent

To disable all logging:

    cumulus@switch:~$ netq config del agent loglevel 
    cumulus@switch:~$ netq config restart agent


<article id="html-search-results" class="ht-content" style="display: none;">

</article>

<footer id="ht-footer">

</footer>
