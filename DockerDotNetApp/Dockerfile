FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build

WORKDIR pruebajaja


EXPOSE 80
EXPOSE 5024

#COPY PROJECT FILES
COPY ./DockerDotNetApp.csproj ./

RUN dotnet restore

#COPY EVERYTHING ELSE

COPY . .
RUN dotnet publish -c Release -o out

#Build image
FROM mcr.microsoft.com/dotnet/sdk:8.0
#FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS runtime
WORKDIR /pruebajaja
COPY --from=build  /pruebajaja/out .
ENTRYPOINT ["dotnet", "DockerDotNetApp.dll"]

# Agregar a program.cs despues de var builder

# // Configurar el puerto directamente
# builder.WebHost.UseUrls("http://*:5024");

#Comandos
# podman build -t imagejajadotnet .
# podman run -d -p 5024:5024 --name pruebadotnet localhost/imagejajadotnet