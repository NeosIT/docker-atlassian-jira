
## Configuration

You can configure a small set of things by supplying the following environment variables

| Environment Variable   | Description |
| ---------------------- | ----------- |
| X_PROXY_NAME           | Sets the Tomcat Connectors `ProxyName` attribute |
| X_PROXY_PORT           | Sets the Tomcat Connectors `ProxyPort` attribute |
| X_PROXY_SCHEME         | If set to `https` the Tomcat Connectors `secure=true` and `redirectPort` equal to `X_PROXY_PORT`   |
| X_PATH                 | Sets the Tomcat connectors `path` attribute |
| X_CROWD_SSO            | Set to `true` to enable SSO via Atlassian Crowd

## How to enable SSO via Crowd

Setting X_CROWD_SSO to `true` will do two things:

- enable the *SSOSeraphAuthenticator*
- tell JIRA to load `crowd-properties.conf` from `/var/atlassian/jira` **(It is your responsibility to put it there!)**

**Warning:** You have to setup the Crowd user directory in JIRA beforehand. After enabling the *SSOSeraphAuthenticator*, you are not able to log in using local accounts anymore.

See the [official Documentation](https://confluence.atlassian.com/crowd/integrating-crowd-with-atlassian-jira-192625.html) for more information.


This image is based on https://github.com/cptactionhank/docker-atlassian-jira