# PaginationSdlBsso

Paquete NuGet para la paginación de consultas en Entity Framework Core compatible con SQL Server, PostgreSQL, MySQL y Oracle. Facilita la gestión de resultados paginados para mejorar la eficiencia de las aplicaciones.

## Instalación

Para instalar el paquete `PaginationSdlBsso` en tu proyecto, usa el siguiente comando en la terminal o en el **Package Manager Console** de Visual Studio:

```bash
dotnet add package PaginationSdlBsso


Ejemplo de uso
Asegúrate de agregar el siguiente using al principio de tu archivo de código:

csharp
Copiar código
using Pagination.Extensions;

Luego, en tu controlador de API, puedes usar el siguiente código para obtener los elementos paginados:


[HttpGet]
public async Task<IActionResult> GetItems(int pageNumber = 1, int pageSize = 10)
{
    var paginatedResult = await _context.Items
        .ToPaginatedListAsync(pageNumber, pageSize);

    return Ok(paginatedResult);
}

Descripción del código:
GetItems: Este método obtiene los elementos desde la base de datos de manera paginada.
ToPaginatedListAsync: Es el método de extensión que se aplica a la consulta Items de tu DbContext, y recibe los parámetros pageNumber y pageSize para determinar qué resultados devolver.
El resultado paginatedResult contiene:
Items: Una lista de los elementos de la página solicitada.
TotalCount: El número total de elementos en la base de datos.
PageSize: El número de elementos por página.
PageNumber: El número de la página actual.
Contribuciones
Las contribuciones son bienvenidas. Si tienes ideas o mejoras para este paquete, por favor abre un issue o un pull request.

Licencia
Este proyecto está licenciado bajo la Licencia MIT - consulta el archivo LICENSE para más detalles.
