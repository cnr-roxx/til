# Turn off portlet success message
2016-09-23

If you want to turn off Liferay's success message in your portlet, just add to portlet.xml:
```
<init-param>
    <name>add-process-action-success-action</name>
    <value>false</value>
</init-param>
```
