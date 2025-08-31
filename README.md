# Modelos 3D del Centro de Innovación y Tecnología (CIT)

**Universidad del Valle de Guatemala**
**Facultad de Ingeniería**
**Departamento de Ciencias de la Computación**

Este repositorio contiene los modelos 3D del edificio principal del **Centro de Innovación y Tecnología (CIT)** de la UVG.
El propósito es disponer de geometrías optimizadas para su uso en **Unity**, específicamente en la simulación de navegación, mapeo y rutas con **NavMesh**.

## Estructura del repositorio

La organización se realiza por niveles del edificio.
Cada carpeta incluye tanto los archivos de modelado paramétrico (Inventor) como las exportaciones optimizadas y los escaneos LIDAR:

```text
├─ Inventor/
│  ├─ CIT-Floor-1.ipt                ← Modelo paramétrico en Autodesk Inventor
│  └─ CIT-Floor-2.ipt
├─ exports/
│  ├─ CIT-1.fbx                ← Exportación optimizada para Unity
│  └─ CIT-2.fbx                
├─ lidar/
│  ├─ floor1/
│  │  ├─ scan_areaA.glb         ← Escaneo parcial con Polycam (GLB)
│  │  └─ scan_areaB.glb
│  └─ floor2/
│     └─ scan_areaC.glb
```

---

## Objetivo del modelado

- Replicar con precisión la geometría de cada piso: paredes, suelos y límites.
- Mantener proporciones basadas en planos arquitectónicos y verificación en el CIT.
- Integrar información de **escaneos LIDAR (.glb)** para corregir inconsistencias dimensionales.
- Simplificar la **malla 3D** mediante reconstrucción CAD en Inventor, reduciendo complejidad y optimizando el rendimiento en motores 3D.
- Facilitar futuras modificaciones o ampliaciones en el modelo.

## Estado actual

- [ ] Nivel 1
- [ ] Nivel 2
- [ ] Nivel 3
- [ ] Nivel 4
- [ ] Nivel 6
- [ ] Nivel 7

## Flujo de trabajo

1. **Referencia inicial**

   * Se parte de los **planos arquitectónicos originales** como guía de diseño.

2. **Validación en sitio**

   * Se detectaron discrepancias notables entre planos y dimensiones reales.

3. **Escaneo LIDAR (Polycam)**

   * Generación de mallas **GLB** por áreas de cada nivel.
   * Precisión aproximada: **±12–30 cm** frente a medidas reales.

4. **Reconstrucción en Inventor**

   * A partir del plano + escaneo se modela un nivel paramétrico en Inventor.
   * Esto **simplifica exponencialmente la malla**, haciéndola ligera y editable.

5. **Exportación para Unity**

   * El modelo de Inventor se exporta a **OBJ**.
   * En **Blender** se corrige origen, pivote y escala.
   * Finalmente se exporta a **FBX** → formato estándar para Unity.
   * El FBX se integra en Unity y se utiliza para generar el **NavMesh** de navegación.
