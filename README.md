# podman-dotnet

Para exponer el puerto usar estas dos opcions:

## **Agregar a program.cs despues de var builder**

```csharp
// Configurar el puerto directamente
builder.WebHost.UseUrls("http://*:5024");
```

## **Agregar al archivo appsetting.json**

```json
"Kestrel": {
  "Endpoints": {
    "Http": {
      "Url": "http://*:5024"
    }
  }
}
```
