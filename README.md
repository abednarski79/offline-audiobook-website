# offline-audiobook-website

## Configuraiton

This applicaiton requires server to support wildcard domain functionality, in other words following 2 URL:

some_random_name.myapp.host.com
other_random_name.myapp.host.com

must be handled by `myapp`

To achieve this result follwing settings mu be added:
- default host on Tomcat server needs to be set to "myapp.host.com"
`<Engine name="Catalina2" defaultHost="www.audiobook.appbucket.eu">`
- one of the the virtual hosts must match exactly this name:
`<Host name="www.audiobook.appbucket.eu"  appBase="audiobook.appbucket.eu" unpackWARs="true" autoDeploy="false">`
- DNS must be set to:
`*.audiobook.appbucket.eu	A server_ip`
