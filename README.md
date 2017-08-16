# dockerddcoms
dockerddcoms

#### Deploy and Visualize

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2F/raw.githubusercontent.com%2Fdwaiba%2Fdockerddcoms%2Fmaster%2Fdeploy.tmpl" target="_blank"><img alt="Deploy to Azure" src="https://raw.githubusercontent.com/dwaiba/dockerddcoms/master/dockerce4azure.png" /></a>



<a href="http://armviz.io/#/?load=https%3A%2F%2F/raw.githubusercontent.com%2Fdwaiba%2Fdockerddcoms%2Fmaster%2Fdeploy.tmpl" target="_blank">  <img src="https://raw.githubusercontent.com/dwaiba/dockerddcoms/master/visualize.png" /> </a>

**[OMS Injection on top of Template Docker EE for Azure](https://aka.ms/azureddc).**

#### Prerequisites

* [Containerized helper-script to help create the Service Principal](https://docs.docker.com/docker-for-azure/#service-principal)
 * Obtain App ID
 * Obtain App Secret
 
  <code> $ docker run -ti docker4x/create-sp-azure sp-name rg-name rg-region</code>
  
* [Obtain Workspace ID and Key for OMS Solutions](https://github.com/dwaiba/dockerddcoms/blob/master/README.md#usage-of-operational-management-suite)
 * Deploy the above mentioned solutions.
 * Obtain OMS Workspace ID
 * Obtain Workspace Key
 
 
#### Usage of Operational Management Suite
**OMS Setup is via the OMS Workspace Id and OMS Workspace Key as per the steps below.**

[Create a free account for MS Azure Operational Management Suite with workspaceName](https://login.mms.microsoft.com/signin.aspx?signUp=on&ref=ms_mms)

* Provide a Name for the OMS Workspace.
* Link your Subscription to the OMS Portal.
* Depending upon the region, a Resource Group would be created in the Sunscription like "mms-weu" for "West Europe" and the named OMS Workspace with portal details etc. would be created in the Resource Group.
* Logon to the OMS Workspace and Go to -> Settings -> "Connected Sources"  -> "Linux Servers" -> Obtain the Workspace ID like <code>ba1e3f33-648d-40a1-9c70-3d8920834669</code> and the "Primary and/or Secondary Key" like <code>xkifyDr2s4L964a/Skq58ItA/M1aMnmumxmgdYliYcC2IPHBPphJgmPQrKsukSXGWtbrgkV2j1nHmU0j8I8vVQ==</code>
* Add The solutions "Agent Health", "Activity Log Analytics" and "Container" Solutions from the "Solutions Gallery" of the OMS Portal of the workspace.
* While Deploying the Docker for Azure Template just the WorkspaceID and the Key are to be mentioned and all will be registered including all containers in any nodes of the Docker for Azure auto cluster.
* Then one can login to https://OMSWorkspaceName.portal.mms.microsoft.com/#Workspace/overview/solutions/details/index?solutionId=Containers and check all containers running for Docker for Azure and use Log Analytics and if Required perform automated backups of the APK Based sys using the corresponding Solutions for OMS.




#### Note on Docker EE and Docker CE for Azure

Presently Docker is using the docker4x repository for entirely private images with dockerized small footprint go apps for catering to standard design of Docker CE and Docker EE for Public Cloud. The following are the last ones for Azure including the ones used for Docker Azure EE (DDC) and Docker CE. The base system service stack of Docker for CE and EE can be easily obtained via any standard monitoring like OMS or names obtained via
<code>docker search docker4x --limit 100|grep azure</code>

* [docker4x/upgrademon-azure](https://hub.docker.com/r/docker4x/upgrademon-azure)
* [docker4x/requp-azure](https://hub.docker.com/r/docker4x/requp-azure)
* [docker4x/upgrade-azure](https://hub.docker.com/r/docker4x/upgrade-azure)
* [docker4x/upg-azure](https://hub.docker.com/r/docker4x/upg-azure)
* [docker4x/ddc-init-azure](https://hub.docker.com/r/docker4x/ddc-init-azure)
* [docker4x/l4controller-azure](https://hub.docker.com/r/docker4x/l4controller-azure)
* [docker4x/create-sp-azure](https://hub.docker.com/r/docker4x/create-sp-azure)
* [docker4x/logger-azure](https://hub.docker.com/r/docker4x/logger-azure)
* [docker4x/azure-vhd-utils](https://hub.docker.com/r/docker4x/azure-vhd-utils)
* [docker4x/l4azure](https://hub.docker.com/r/docker4x/l4azure)
* [docker4x/waalinuxagent](https://hub.docker.com/r/docker4x/waalinuxagent) (dated)
* [docker4x/meta-azure](https://hub.docker.com/r/docker4x/meta-azure)
* [docker4x/cloud-azure](https://hub.docker.com/r/docker4x/cloud-azure)
* [docker4x/guide-azure](https://hub.docker.com/r/docker4x/guide-azure)
* [docker4x/init-azure](https://hub.docker.com/r/docker4x/init-azure)
* [docker4x/agent-azure](https://hub.docker.com/r/docker4x/agent-azure)

