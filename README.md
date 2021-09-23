![AnalyticsServerConf (1)](https://user-images.githubusercontent.com/37985054/131468123-2ac3b96c-d977-4182-add4-8ebcc0608600.jpg)
# Code Analytics Server Pack in Docker
## Used tools:
- [Gitea](https://gitea.io/en-us/)
- [SonarQube](https://www.sonarqube.org/)
- [Jenkins](https://www.jenkins.io/)

## Install Docker and container
###### Help with [Docker documentation](https://docs.docker.com/get-docker/).

1. Download the repository 
2. Open terminal
3. Go to path
4. Enter 'docker-compose -p code_analytics_server_pack up'
5. and use

## Used ports:
- Gitea: [3000](http://localhost:3000/)
- SonarQube: [9000](http://localhost:9000/)
- Jenkins: [8080](http://localhost:8080/)

# Server configuration
All servers must be configured on first run.
<br/>
<br/>
## Gitea
- Add new accont
- Create new organizations
<br/>
<br/>
## Jenkins
### Install plugins. "Dashboard -> Manage Jenkins -> Plugin Manager -> Available"
Select:
- Gitea
- SonarQube Scanner

and restart
<br/>
<br/>

### Config Gitea connection:
- Add server
    - Go to "Dashboard -> Manage Jenkins -> Configure System"
    - Scroll down to "Gitea Servers"
    - Server URL: "http://<Gitea_container_name>:3000"
    - <font color="green"> Save </font>
- Add new item
    - Add name
    - Select "Gitea Organization"
    - Projects->Server: select server
    - Projects->Credentials: add your Gitea user
    - Projects->Owner: Enter Gitea organizations name
    - <font color="green"> Save </font>
<br/>
<br/>
## SonarQube
### Install plugin.
- C# Code Quality and Security