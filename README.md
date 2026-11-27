# Proceso de Apelación – UGEL Tarma

Modelado de negocio del recurso administrativo de apelación en la UGEL Tarma, hecho en **IBM Rhapsody** para el curso de **Análisis y Diseño de Sistemas**.

El proceso empieza cuando el administrado presenta su escrito de apelación en la UGEL Tarma. La UGEL revisa el expediente y lo remite a la DRE Junín, que lo resuelve. La resolución vuelve a la UGEL, que la notifica al administrado, y el proceso termina cuando este firma el cargo.

## Resumen en cifras

| Elemento | Cantidad | Detalle |
|---|---|---|
| Actor externo | 1 | Administrado (quien presenta la apelación) |
| Business Workers | 10 | Trabajadores del negocio en UGEL Tarma y DRE Junín |
| Business Entities | 9 | Documentos del proceso (escrito, oficio, resolución, etc.) |
| Actividades | 28 | 24 numeradas (01–24) + 4 complementarias |
| Calles (swimlanes) | 11 | 1 actor + 10 business workers |
| Estados del expediente | 6 | Desde *Registrado en UGEL* hasta *Notificado* |

## Actor y Business Workers

El único **actor** es el **Administrado**: inicia el proceso y lo cierra al recibir la resolución.

Los **10 Business Workers** son quienes ejecutan las actividades dentro de la institución:

| Business Worker | Qué hace | Actividades |
|---|---|---|
| Responsable de Mesa de Partes | Revisa requisitos, registra en el SITD, concede 2 días para subsanar o declara el escrito no presentado, recibe la resolución | 02, 03, 22 y complementarias |
| Secretaría de Asesoría Jurídica | Recibe el expediente, elabora hoja de coordinación, oficio y formato, remite a la DRE, comunica, publica y notifica | 04, 05, 08, 09, 11, 16, 17, 23, 24 |
| Responsable de Archivo UGEL | Recibe la hoja de coordinación y busca la autógrafa | 06, 07 |
| Jefe de Asesoría Jurídica | Visa el oficio y el formato | 10 |
| Secretaría de Dirección | Recibe, numera y devuelve el expediente | 12, 14, 15 |
| Director de la UGEL | Firma el oficio y el formato | 13 |
| Encargado de Trámite Documentario DRE | Recibe, numera y deriva el expediente en la DRE | 18 |
| Director de Asesoría Jurídica DRE | Revisa el expediente y elabora el proyecto de resolución | 19 |
| Director Regional DRE | Firma el proyecto de resolución | 20 |
| Responsable de Archivo DRE | Numera, fecha, archiva y remite la resolución a la UGEL | 21 |

## Business Entities

Los 9 documentos que se generan o usan en el proceso:

1. Escrito de Apelación
2. Hoja de Coordinación
3. Autógrafa de la Resolución Impugnada
4. Oficio de Remisión
5. Formato de Trámite de Apelación
6. Expediente de Apelación
7. Proyecto de Resolución
8. Resolución Directoral Regional
9. Cédula de Notificación

## Actividades

El diagrama contiene **28 actividades**, **2 decisiones** y **2 nodos finales**.

- **Flujo principal:** 24 actividades numeradas del 01 al 24.
- **Complementarias (4):**
  - Concede 2 días para subsanar
  - Declara el escrito no presentado
  - Presenta la subsanación
  - Recibe la resolución y firma el cargo

## Diagramas

### 1. Diagrama de Clases de Negocio

Muestra los 10 Business Workers y las 9 Business Entities. El **Expediente de Apelación** es la entidad central: reúne el escrito, el oficio, el formato, la hoja de coordinación y la autógrafa. El proceso termina en la **Resolución Directoral Regional** y la **Cédula de Notificación**.

### 2. Diagrama de Actividades (proceso actual)

Es el diagrama principal y está dividido en 11 calles, una por participante.

1. El Administrado presenta el escrito y Mesa de Partes revisa los requisitos.
2. Si falta algo, se le dan 2 días para subsanar; si no subsana, el escrito se declara no presentado.
3. Si cumple, el expediente pasa por Asesoría Jurídica, Archivo y Dirección de la UGEL (visado, firma y numeración).
4. La UGEL remite el expediente a la DRE Junín, donde se elabora y firma la resolución.
5. La resolución vuelve a la UGEL, que la comunica, publica y notifica al administrado.

### 3. Diagrama de Estados del Expediente

Ciclo de vida del expediente en 6 estados:

```
Registrado en UGEL → Remitido a DRE → En evaluación en DRE → Resuelto por DRE → Resolución recibida en UGEL → Notificado al administrado
```

## Para qué sirve el modelo

Deja claro quién hace qué, con qué documentos y en qué estado está el expediente. Eso facilita detectar demoras y proponer mejoras al proceso.

## Modelo en Rhapsody

> **Borrador:** el modelo todavía se está modificando.

El proyecto de IBM Rhapsody está en [`modelo/UGELTarma_apelacion.zip`](modelo/UGELTarma_apelacion.zip).

Para abrirlo:

1. Descarga y descomprime el zip.
2. En IBM Rhapsody, abre `UGELTarma_apelacion/UGELTarma_apelacion.rpyx`.

## Autores

- [Sadge03](https://github.com/Sadge03)
- [CaptainBoar](https://github.com/CaptainBoar)
