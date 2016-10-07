#Add event listener to dom element

To fire a function on element's change, add to JSP following code:

```javascript
<script>
    AUI().use(function (A) {
        var autocompleterKeywordsField = A.one('#<portlet:namespace />keywords');
        var originalKeywordsField = A.one('#_3_keywords');
        autocompleterKeywordsField.on('change', function(e){
            if (originalKeywordsField != null)
                originalKeywordsField.set('value', autocompleterKeywordsField.get('value'));
        });
    }
</script>

or on select-event:

```javascript
    autocomplete.on('select', function (e) {
            var viewUrl = e.result.raw.viewUrl;
            window.location = viewUrl;
    });
```