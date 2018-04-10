# PiMaven

## Bare Maven project set up for easy building and deploying by ssh to a remote Linux system, like a Raspberry Pi.

NetBeans has in-built support for deploying and running code on a remote system, but that is not available for Maven projects. The pom file in this project uses the exec plugin and PuTTY to copy the built artefacts to the remote system. 

### Requiremens

* PuTTY
* Ssh enabled on remote Linux system

### Configuration

The pom loads connection parameters from `pi-deploy.properties`. Take the included `pi-deploy.example.properties`, fill in the correct values and rename it to `pi-deploy.properties`. Try not to commit it as it includes the ssh password for the remote system.

On the remote system, create directory `${pi.remote.directory}/${project.artifactId}` as PuTTY will not create the whole directory path, at least not in one go.

### Building

Select profile `pi-deploy` and build the project. Use the profile only for building, it will not work for running. Just ssh to the remote system and run manually.

### Enjoying

Let out a sigh of relief as you realize you can use all the benefits of Maven while being able to quickly and easily deploy to your Raspberry Pi.
