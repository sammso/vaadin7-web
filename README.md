# Vaadin 7 web README

This is example how to integrate Vaadin 7 to Liferay as plugin. 
Vaadin 6 has been bundled to Liferay 6.0 onwards, but Vaadin 7 is not. 
This version does not support co-existense of Vaadin 6 and Vaadin 7.

Plugin contains only Vaadin themes and widget sets. Not jar etc.

It has to be configured through portal-ext.properties to make it work.

```
##
## Vaadin
##

    #
    # Specify the location of the portal wide Vaadin themes and widget set
    # (client side JavaScript).
    #
    vaadin.resources.path=/vaadin7-web
```

NOTE: Note this does not support **liferay-plugin-package.properties's portal-dependency-jars** setting for vaadin dependencies. So you need to include those to your project manually.

## Compile and deploy:

Change the bundle root from pom.xml to point root folder of your Liferay 6.2 bundle. 

The location has been marked, with following comment:

```
<!-- POINT THIS TO YOUR BUNDLE ROOT -->
```
and run

```
mvn package
mvn liferay:deploy
```

## Verify

You can verify that plugin is working by with following example app: 

https://github.com/sammso/vaadin7-sample-portlet