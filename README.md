# podman-dotnet

## Imagenes oficiales de .NET SDK: https://hub.docker.com/_/microsoft-dotnet-sdk/

## Imagen de .NET 3.1: podman pull mcr.microsoft.com/dotnet/core/sdk:3.1

Proyecto para colocar en un contenedor un proyecto de .NET 8 y ejecutarlo usando PODMAN, video de referencia: https://www.youtube.com/watch?v=8WO-WlZ9NoA&list=WL&index=1

# Para exponer el puerto usar cualquiera de estas dos opciones:

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
