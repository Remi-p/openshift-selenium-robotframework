Making selenium/node-chrome work with open shift.

Inspirations :
* [ddavison/docker-selenium-ephemeral](https://github.com/ddavison/docker-selenium-ephemeral)
* [move the creation of the config.json file into a RUN directive SeleniumHQ/docker-selenium#185](https://github.com/SeleniumHQ/docker-selenium/pull/185/files)
* [Selenium Hub keeps crashing](https://github.com/ddavison/selenium-openshift-templates/issues/1)

Typically, deleting the following line in `selenium/node-base`, `entry_point.sh` :
```
/opt/selenium/generate_config > /opt/selenium/config.json
```


And adding in `selenium/node-chrome`, `Dockerfile`, just before the `USER seluser` :
```
RUN /opt/selenium/generate_config > /opt/selenium/config.json
```
