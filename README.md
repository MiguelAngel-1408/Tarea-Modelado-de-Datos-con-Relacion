# Tarea-Modelado-de-Datos-con-Relacion

# Relación entre Autor y Libro

Esta tara define dos entidades principales:

- **Autor**: Representa a un autor que puede haber escrito varios libros.
- **Libro**: Representa un libro que tiene un único autor.

## Relación

La relación entre **Autor** y **Libro** es de **uno a muchos (1:N)**, lo que significa que:
- Un **Autor** puede escribir varios **Libros**.
- Un **Libro** pertenece a un solo **Autor**.

## Implementación

- En la clase `Autor`, se usa `@OneToMany(mappedBy = "autor", cascade = CascadeType.ALL, orphanRemoval = true)`, lo que indica que un autor puede tener varios libros.
- En la clase `Libro`, se usa `@ManyToOne @JoinColumn(name = "autor_id", nullable = false)`, lo que establece la relación con `Autor`.

Este diseño permite que cuando se elimine un **Autor**, todos sus **Libros** asociados también sean eliminados automáticamente.
