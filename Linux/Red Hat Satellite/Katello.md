<h1> What is Katello</h1>
Katello is an open source version of Red Hat Satellite.
You may be wondering well what is Red Hat Satellite, well RedHat Satellite is a paid subscripation manager which allows patch management / configuration for redhat servers 

Red Hat Satellite version 5 is based on SpaceWalk, the current version of Red Hat Satellite 6 is based on foreman with katello plugins. 
The most important core components are 
- pulp, 
- candlepin, 
- qpid
- puppet





Katello Patch Management or Foreman with Katello, is one of the components of the upstream version of Red Hat Satellite, Katelo is a life cycle management plugin for Foreman. Katello allows managing thousands of machines in a single click. It pulls content from remote repositories into an isolated environment and makes the subscription's management easy for us.




Foreman:
is an open source software/program used for provisioning and life cycle management of physical and virtual systems.
Foreman automatically configures these systems using various methods including.


Katelo: 
is a subscription and repoistory Managment application, It provides a means to subscribe to Redhat repositories and download content.
Katelo is an extension in Foreman


- Candlepin: 
Is a service within Katello that handles subscription managment

- Pulp:
Is a service within katello that handles repostiory and content managment

- Hammer:
Is a Command Line Tool (CLI) that provides command line and shell equivalents of most WEB UI funcitons.

- REST API:
Red Hat Satelite 6 includes a RESTful API service that allows system administrators and developers to write custom scripts and thrid-part applications that interact with RedHat satelite

- Capsule:
Red Hat capsule Server acts as a proxy for some of the main Satelite including repository storage, DNS, DHCP and puppet master configuration. Each Server also contains intergrated Capsule Server services.




------------- Foreman & Katelo Setup ---------------

Step 1: 
- localectl status
 - localectl set-locale LC_CTYPE=en_US.utf8

Step 1.1:
- hostnamectl set-hostname foreman.faze.local
 - echo 192.168.244.143 foreman.faze.local foreman localhost >> /etc/hosts
   - dnsdomainame -f

Step 2: Install Chronyc service & check chronyc sources, enable ntp.
- yum install chronyc -y
  - chronyc sources
  - timedatectl set-ntp true

Step 2.1: Add ports to firewall
  - firewall-cmd --add-port={53,80,443,5647,9090}/tcp --permanent
  - firewall-cmd --add-port={67-69,53}/udp --permanent
  - firewall-cmd --reload