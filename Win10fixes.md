### Enable safe mode via CMD
```bcdedit /set {default} safeboot minimal``` 
### Disable safe mode via CMD
```bcdedit /deletevalue {current} safeboot```
