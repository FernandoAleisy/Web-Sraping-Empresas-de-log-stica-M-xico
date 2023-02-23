# Web-Sraping-Empresas-de-logística-México
Se realizo web scraping de la página SIEM (Sistema de información empresarial de México). Se extrajeron datos de las empresas registradas en la Cámara Nacional del autotransporte de carga
---
Analizando la página:

1° Se busca la camara a la que pertenecen las industrias:

![Screenshot_2](https://user-images.githubusercontent.com/77293107/220796512-b2b9ccfe-d9bf-42e8-9743-dd9f5e3aa7ae.png)

2° Se da clic derecho y se selecciona la opción inspeccionar:

![image](https://user-images.githubusercontent.com/77293107/220794943-2e4d2ca9-749a-409d-8e10-2145494d23a4.png)

3° Se selecciona la opción Network, dentor de la inspección:

![Screenshot_3](https://user-images.githubusercontent.com/77293107/220796269-9b143b0f-ea43-4f32-962f-c3da77969c07.png)

4° Estando en Network se realiza la busqueda para ver cómo la página realia la consulta:
![image](https://user-images.githubusercontent.com/77293107/220795758-7545df11-7ee1-422d-84b0-aa266b25171b.png)

5° Damos clic en la consulta para ver la url con la que se realizará el web scraping:

![Screenshot_3](https://user-images.githubusercontent.com/77293107/220796645-e048d6bd-1295-43d0-8270-29fdbdc12ac3.png)

![Screenshot_6](https://user-images.githubusercontent.com/77293107/220796886-7572e689-6037-4526-82de-38e043b4e250.png)

6° Se obtiene la siguiente url, la cual es una consulta que devuelve un .json:

https://siem.economia.gob.mx/establecimientos-publicos-x-criterios?id=&catEntidadFederativaFk=0&catActividad=0&catCamaraFk=~Jf3KrDTdu63&nombreComercial=&importa=2&exporta=2&publico=2&catEdoEstablecimientoFk=0&pageNum=1&orderBy=&desc=0

7° Si se cambia el pageNum=1 por pageNum=0 y se abre la url resultante:

https://siem.economia.gob.mx/establecimientos-publicos-x-criterios?id=&catEntidadFederativaFk=0&catActividad=0&catCamaraFk=~Jf3KrDTdu63&nombreComercial=&importa=2&exporta=2&publico=2&catEdoEstablecimientoFk=0&pageNum=0&orderBy=&desc=0

Se obtiene los siguientes datos, los cuales son importante para extraer información útil de las empresas:

![image](https://user-images.githubusercontent.com/77293107/220798045-856f7486-9588-463e-8e66-8b2f75b6418e.png)

Ahora sabemos el número de empresas registradas en esta cámara y el número de páginas que podemos consultar cambiando el parametro pageNum=0 por los números 1,2,3,... o 334

8° Ahora realicemos la consulta a la primera página (pageNum=1):

https://siem.economia.gob.mx/establecimientos-publicos-x-criterios?id=&catEntidadFederativaFk=0&catActividad=0&catCamaraFk=~Jf3KrDTdu63&nombreComercial=&importa=2&exporta=2&publico=2&catEdoEstablecimientoFk=0&pageNum=1&orderBy=&desc=0

Del primer .json se puede obtener el ID de la empresa (muy importante) y el nombre comercial:

![image](https://user-images.githubusercontent.com/77293107/220799358-b87a1c21-23a7-4898-ab54-52f5e383045b.png)

9° Volvemos a la página donde realizamos la buqueda y damos clic en la lupa de la primera empresa:

![image](https://user-images.githubusercontent.com/77293107/220798692-71c80087-7be3-46ff-9f7e-d2bbaa4c5543.png)

En la página de la empresa se puede ver que la url termina en el ID de la empresa:

![image](https://user-images.githubusercontent.com/77293107/220798809-a8f72851-1d9c-4f98-862b-22dbc55b105f.png)
---
Con estas url tenemos todas las herramientas para empezar a hacer el web scraping

