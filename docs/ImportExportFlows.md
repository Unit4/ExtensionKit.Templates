## Import/Export flows

### Getting Started

Using the [U4.ExtensionsKit.PowerShell](..git s/docs/U4ExtensionsKitPowershellModule.md) module you can **import flows** to your tenant and also to **export** them. Use the link to get started.

### Import flow

You can import flows together with your defined parameters to your tenant using the commandlet `Import-U4EKFlow`:
```
Import-U4EKFlow -TemplateFile "C:\Users\ekuser\Desktop\exportedflow.json" -ParameterFile "C:\Users\ekuser\Desktop\exportedparameters.json"
```

### Export flow

You can also export your flows together with the parameters you've defined using the commandlet `Export-U4EKFlow`:

```
Export-U4EKFlow -FlowId bb493cc3-fake-4b55-ac17-36a741c5e9bb -TemplateFile "C:\Users\ekuser\Desktop\exportedflow.json"
```