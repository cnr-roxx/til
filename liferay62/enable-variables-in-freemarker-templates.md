# Enable Variables In Freemarker Templates

Access to many important portal variables from Freemarker templates is disabled in Liferay 6.2 by default. To gain access to these variables insert following lines into _portal-ext.properties_ file:

```properties
# Freemarker template settings
freemarker.engine.restricted.variables=
```
