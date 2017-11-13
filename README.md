# Dynamics 365 Snippets
JS snippets for Dynamics 365

## Table of contents
- [Disable field in editable grid](#)

## Disable field in editable grid
Add as OnRecordSelect handler, select execution context.

```javascript
function disableFieldName(context) {
    context.getFormContext().getData().getEntity().attributes.forEach(function (attr) {
        if (attr.getName() === "FieldName") {
            attr.controls.forEach(function (c) {
                c.setDisabled(true);
            })
        }
    });
}
```
