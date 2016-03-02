# Switch Portal To Developer Mode

To switch off various optimization features which makes difficult debuging put these lines into _portal-ext.properties_:

```properties
# BEG: dev mode

# Toogle merging CSS files into one big file (equiv. URL parameter: css_fast_load=0)
theme.css.fast.load=false

# Toogle merging js scripts into one big file (equiv. URL pareameter: js_fast_load=0)
javascript.fast.load=false
javascript.log.enabled=false

theme.images.fast.load=false

layout.template.cache.enabled=false

browser.launcher.url=

combo.check.timestamp=true

freemarker.engine.cache.storage=soft:1
freemarker.engine.resource.modification.check.interval=0

log.sanitizer.enabled=false

minifier.enabled=false

openoffice.cache.enabled=false

com.liferay.portal.servlet.filters.cache.CacheFilter=false
com.liferay.portal.servlet.filters.etag.ETagFilter=false
com.liferay.portal.servlet.filters.header.HeaderFilter=false
com.liferay.portal.servlet.filters.themepreview.ThemePreviewFilter=true

# Tooggle minimizing of HTML code (equiv. URL parameter: strip=0)
com.liferay.portal.servlet.filters.strip.StripFilter=false

# END: dev mode
```
