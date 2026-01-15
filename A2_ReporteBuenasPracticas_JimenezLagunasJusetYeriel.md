# Actividad 2 — Reporte de Buenas Prácticas y Documentación de Código

---

**Alumno:** Jimenez Lagunas Juset Yeriel  
**Grupo:**  2DSM-G3  
**Unidad:** 1°

---

## 1. Objetivo del reporte
- Explicar las buenas prácticas de codificación que permiten desarrollar software legible, mantenible y escalable.
- Detallar los estándares y herramientas para la documentación adecuada de programas, facilitando el trabajo en equipo y la actualización de proyectos.

---

## 2. Buenas prácticas de codificación

### 2.1 Nombres de variables
- **Reglas:** Deber reflejar el propósito o contenido del elemento; usar convenciones según el lenguaje (snake_case para Python, camelCase para Java); evitar nombres genéricos como a, b o funcion1.
- **Ejemplo:** En lugar de `f(a, b)`, usar `calcular_area_rectangulo(base, altura)`; en lugar de `c`, usar `area`.


### 2.2 Comentarios
- **Cuándo comentar:** Para explicar el "por qué" de una acción, documentar partes complejas o decisiones de diseño importantes.
- **Qué evitar:** Comentarios obvios que repiten lo que dice el código; comentarios largos o desactualizados; usar comentarios para ocultar código innecesario.


### 2.3 Estructura del código
- **Indentación:** Usar 4 espacios por defecto; mantener consistencia en todo el proyecto para mejorar legibilidad.
- **Modularidad:** Dividir el código en módulos, funciones o clases según su funcionalidad; evitar bloques de código muy largos (no exceder las 50 líneas por función).
- **Evitar duplicidad:** Reutilizar código mediante funciones o clases en lugar de copiar y pegar; centralizar lógica repetitiva.

---

## 3. Documentación del código

### 3.1 Estándares
- **Estándar elegido:** Para Python, formato Google de docstrings; para Java, Javadoc.
- **Elementos recomendados:** Descripción general; parámetros de entrada (tipo, nombre y propósito); valores de retorno (tipo y descripción); errores o excepciones generadas; autor, versión y fecha (si aplica).


### 3.2 Herramientas / enfoque
- **README / generadores / extensiones:** README.md para describir el proyecto; Sphinx o pdoc para generar documentación de Python; Javadoc como herramienta integrada para Java; Doxygen para lenguajes como C++.
- **Ventajas:** Permite acceder rápidamente a la información del código; facilita la integración con otros desarrolladores; genera documentación en formatos legibles (HTML, PDF).

---

## 4. Ejemplos prácticos

### 4.1 Antes / Después (Ejemplo 1)
**Antes:**
```python
# Cálculo
def f(a, b):
    # Operación
    c = a * b
    # Devolver
    return c
```

**Después:**
```python
"""Calcula el área de un rectángulo a partir de su base y altura."""
def calcular_area_rectangulo(base: float, altura: float) -> float:
    area = base * altura
    return area
```


### 4.2 Antes / Después (Ejemplo 2)
**Antes:**
```java
public static int op(int n1, int n2) {
    if(n2 == 0) {
        System.out.println("Error");
        return 0;
    }
    return n1 / n2;
}
```

**Después:**
```java
/**
 * Realiza la división entera de dos números.
 * @param dividendo Valor que se va a dividir (debe ser entero)
 * @param divisor Valor por el que se divide (no puede ser cero)
 * @return Resultado de la división entera
 * @throws ArithmeticException Si el divisor es igual a cero
 */
public static int realizar_division_entera(int dividendo, int divisor) throws ArithmeticException {
    if (divisor == 0) {
        throw new ArithmeticException("No se puede dividir por cero");
    }
    return dividendo / divisor;
}
```


### 4.3 Ejemplo de documentación
```python
"""
Módulo: gestion_usuarios.py
Propósito: Administrar el registro y consulta de usuarios en un sistema.
Autor: Jimenez Lagunas Juset Yeriel
"""

class Usuario:
    """Clase que representa un usuario del sistema."""
    
    def __init__(self, nombre_usuario: str, correo: str, edad: int):
        """
        Inicializa una instancia de Usuario.
        @param nombre_usuario: Nombre único del usuario (máximo 20 caracteres)
        @param correo: Dirección de correo electrónico válida
        @param edad: Edad del usuario (debe ser ≥ 18)
        @throws ValueError Si la edad es menor a 18 o el nombre de usuario está vacío
        """
        if edad < 18:
            raise ValueError("El usuario debe ser mayor de edad")
        if len(nombre_usuario.strip()) == 0:
            raise ValueError("El nombre de usuario no puede estar vacío")
        
        self.nombre_usuario = nombre_usuario
        self.correo = correo
        self.edad = edad

    def obtener_datos_usuario(self) -> dict:
        """
        Devuelve los datos del usuario en formato diccionario.
        @return Diccionario con claves 'nombre_usuario', 'correo' y 'edad'
        """
        return {
            "nombre_usuario": self.nombre_usuario,
            "correo": self.correo,
            "edad": self.edad
        }
```

---

## 5. Recomendaciones finales
- Aplicar las buenas prácticas desde el inicio del desarrollo, no como paso posterior.
- Revisar y refactorizar el código periódicamente para mantenerlo ordenado y actualizado.
- Usar herramientas de análisis de código (pylint para Python, Checkstyle para Java) para detectar inconsistencias y errores.

---

## 6. Fuentes consultadas
1. Guía de Estilo de Código de Google (Python y Java).
2. Documentación oficial de Python: https://docs.python.org/3/documenting.html
3. Documentación oficial de Java: https://docs.oracle.com/en/java/javase/17/docs/specs/javadoc/doc-comment-spec.html
4. "Clean Code: A Handbook of Agile Software Craftsmanship" de Robert C. Martin.



 
 
 

