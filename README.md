Aplicación de los pilares de la Programación Orientada a Objetos (POO) 
1.Encapsulamiento 
¿Cómo se protege el acceso directo a los atributos de las clases Material y Category? ¿Qué 
mecanismos se usan para acceder y modificar estos datos?
El encapsulamiento se logra de dos maneras clave en tus clases Material y Category:Protección de Atributos: Todos los atributos (campos) de las clases se declaran como private. Esto impide que cualquier otra clase pueda acceder o modificarlos directamente.
2.Abstracción 
¿Qué detalles se ocultan en las clases de servicio (MaterialService, CategoryService) y cómo 
se simplifica el uso de estas funcionalidades desde los controladores?
La abstracción consiste en ocultar la complejidad y exponer solo lo esencial. 
El MaterialService es un ejemplo perfecto de esto:
Detalles Ocultos:◦Persistencia de datos: El MaterialController no tiene idea de que los datos se guardan en una ArrayList en memoria.
Podríamos cambiarlo a una base de datos real (MySQL, PostgreSQL) y el controlador no necesitaría ningún cambio.◦Generación de IDs: La lógica de usar un AtomicLong para generar IDs únicos está completamente oculta dentro del MaterialRepository, que a su vez es utilizado por el MaterialService. El controlador no sabe ni le importa cómo se generan los IDs.Lógica de negocio: Si hubiera reglas complejas (ej: "no se puede registrar un material si su nombre ya existe"), esa lógica estaría dentro del servicio, no en el controlador.
Simplificación para el Controlador:
El controlador solo interactúa con una interfaz simple y de alto nivel.
3.Herencia 
Aunque no se usa herencia explícita en este proyecto, ¿cómo se podría aplicar si se quisiera 
extender el comportamiento de los materiales para incluir tipos especiales?
La herencia se podría usar para crear una jerarquía de materiales, donde cada tipo especial comparte las características base pero añade las suyas propias.
4.Polimorfismo 
¿Dónde se podría aplicar polimorfismo en este proyecto si se agregaran diferentes tipos de 
materiales con comportamientos distintos? 
El polimorfismo (que significa "muchas formas") permitiría tratar a todos los tipos de materiales de manera uniforme, aunque su comportamiento interno sea diferente. 
Se aplica directamente sobre el ejemplo de la herencia.
