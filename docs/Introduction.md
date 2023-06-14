---
layout: default
title: معرفی
nav_order: 1
---

# What is Zabbix
## Overview
Zabbix was created by Alexei Vladishev, and currently is actively developed and supported by Zabbix SIA.

Zabbix is an enterprise-class open source distributed monitoring solution.

Zabbix is a software that monitors numerous parameters of a network and the health and integrity of servers, virtual machines, applications, services, databases, websites, the cloud and more. Zabbix uses a flexible notification mechanism that allows users to configure email based alerts for virtually any event. This allows a fast reaction to server problems. Zabbix offers excellent reporting and data visualization features based on the stored data. This makes Zabbix ideal for capacity planning.

Zabbix supports both polling and trapping. All Zabbix reports and statistics, as well as configuration parameters, are accessed through a web-based frontend. A web-based frontend ensures that the status of your network and the health of your servers can be assessed from any location. Properly configured, Zabbix can play an important role in monitoring IT infrastructure. This is equally true for small organizations with a few servers and for large companies with a multitude of servers.

Zabbix is free of cost. Zabbix is written and distributed under the GPL General Public License version 2. It means that its source code is freely distributed and available for the general public.

Commercial support is available and provided by Zabbix Company and its partners around the world.

Learn more about Zabbix features.

## Users of Zabbix
Many organizations of different size around the world rely on Zabbix as a primary monitoring platform.



# Zabbix features
## Overview
Zabbix is a highly integrated network monitoring solution, offering a multiplicity of features in a single package.

## Data gathering

availability and performance checks
support for SNMP (both trapping and polling), IPMI, JMX, VMware monitoring
custom checks
gathering desired data at custom intervals
performed by server/proxy and by agents
## Flexible threshold definitions

you can define very flexible problem thresholds, called triggers, referencing values from the backend database
## Highly configurable alerting

sending notifications can be customized for the escalation schedule, recipient, media type
notifications can be made meaningful and helpful using macro variables
automatic actions include remote commands
## Real-time graphing

monitored items are immediately graphed using the built-in graphing functionality
## Web monitoring capabilities

Zabbix can follow a path of simulated mouse clicks on a web site and check for functionality and response time
## Extensive visualization options

ability to create custom graphs that can combine multiple items into a single view
network maps
slideshows in a dashboard-style overview
reports
high-level (business) view of monitored resources
## Historical data storage

data stored in a database
configurable history
built-in housekeeping procedure
## Easy configuration

add monitored devices as hosts
hosts are picked up for monitoring, once in the database
apply templates to monitored devices
## Use of templates

grouping checks in templates
templates can inherit other templates
## Network discovery

automatic discovery of network devices
agent autoregistration
discovery of file systems, network interfaces and SNMP OIDs
## Fast web interface

a web-based frontend in PHP
accessible from anywhere
you can click your way through
audit log
## Zabbix API

Zabbix API provides programmable interface to Zabbix for mass manipulations, third-party software integration and other purposes.
Permissions system

secure user authentication
certain users can be limited to certain views
## Full featured and easily extensible agent

deployed on monitoring targets
can be deployed on both Linux and Windows
## Binary daemons

written in C, for performance and small memory footprint
easily portable
## Ready for complex environments

remote monitoring made easy by using a Zabbix proxy



# Zabbix overview
## Architecture
Zabbix consists of several major software components. Their responsibilities are outlined below.

## Server
Zabbix server is the central component to which agents report availability and integrity information and statistics. The server is the central repository in which all configuration, statistical and operational data are stored.

## Database storage
All configuration information as well as the data gathered by Zabbix is stored in a database.

## Web interface
For an easy access to Zabbix from anywhere and from any platform, the web-based interface is provided. The interface is part of Zabbix server, and usually (but not necessarily) runs on the same physical machine as the one running the server.

## Proxy
Zabbix proxy can collect performance and availability data on behalf of Zabbix server. A proxy is an optional part of Zabbix deployment; however, it may be very beneficial to distribute the load of a single Zabbix server.

## Agent
Zabbix agents are deployed on monitoring targets to actively monitor local resources and applications and report the gathered data to Zabbix server. Since Zabbix 4.4, there are two types of agents available: the Zabbix agent (lightweight, supported on many platforms, written in C) and the Zabbix agent 2 (extra-flexible, easily extendable with plugins, written in Go).

## Data flow
In addition it is important to take a step back and have a look at the overall data flow within Zabbix. In order to create an item that gathers data you must first create a host. Moving to the other end of the Zabbix spectrum you must first have an item to create a trigger. You must have a trigger to create an action. Thus if you want to receive an alert that your CPU load is too high on Server X you must first create a host entry for Server X followed by an item for monitoring its CPU, then a trigger which activates if the CPU is too high, followed by an action which sends you an email. While that may seem like a lot of steps, with the use of templating it really isn't. However, due to this design it is possible to create a very flexible setup.