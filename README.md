# Solución prueba técnica Chubb

## Aspectos Técnicos

- El solución se organiza de las siguiente manera:
  
  - ChubbReto.Domain: Contiene la entidades de dominio y la abastracciones del repositorio.
  - ChubbReto.Application: Está estructurado en corte vertical para mejor escalabilidad de features por carpetas, dentro de estos las interfaces de servicios, implementación de servicios y DTOs y objetos compartidos por las diferentes features. Se implementa el Patrón de Servicios y Patrón de resultado para un mejor manejo de errores y excepciones.
  - ChubbReto.Infraestructura: Contiene la implementación la implementaciín de Patrón repositorio indicados por el dominio. Los repositorios están implementados con Dapper.
  - ChubbReto.Web: Contiene el Front desarrollado en MVC(Modelos, vistas y controladores) con pagos Razor(.cshtml). Aqui se configura la inyección de dependencias.

## Instrucciones:

- Descargar el repositorio en maquina local.
- Abrir la solución ChubbReto.sln y restaurar los paquetes nuget.
- Establecer ChubbReto.Web como proyecto de inicio si no lo estuviera.
- Ejecutar el script de base de datos que se encuentra en la carpeta /Database y ejecutar el archivo ChubbReto-Data.sql.
- En el archivo web.config de ChubbReto.Web cambiar la cadena de conexión por los datos del su sql local, reemplazando los datos entre corchetes:
  	<connectionStrings>
    		<add name="DefaultConnection" connectionString="Server=[instancia];Database=CHUBB_RETO;User Id=[usuario];Password=[password];TrustServerCertificate=True;" providerName="System.Data.SqlClient" />
     </connectionStrings>
- Antes de ejecutar el proyecto limipiar la solución (Menú: Build > Build Clean Solución) y compilar (Menú: Build > Build Solution).

## Notas

- La solución está implementada en .NET Framework 4.7.2.
- La configuración de máximo de libros permitidos por autor en el Web.Config está en :
  <appSettings>
    ....
	  <add key="MaxBooksPerAuthor" value="4" />
  </appSettings>
