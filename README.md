# roscados
Biblioteca de anotaciones CNC Fanuc, desbaste, rampas, radios y trigonometría aplicada, #ROSCADOS#
📊 TABLA COMPLETA ROSCAS MÉTRICAS ISO 965 – PARA CICLO G76

================================================================================
ROSCAS MÉTRICAS DE PASO NORMAL (Coarse Pitch)
================================================================================

Rosca    | Paso   | Diam.Fondo | Altura Fil | Q Micras | Notas
---------|--------|------------|------------|----------|------------------
M3 x 0.5 | 0.5    | 2.46       | 0.325      | 325      | Muy pequeña
M4 x 0.7 | 0.7    | 3.14       | 0.454      | 454      | Roscas finas
M5 x 0.8 | 0.8    | 4.02       | 0.520      | 520      | Roscas finas
M6 x 1.0 | 1.0    | 4.77       | 0.650      | 650      | Estándar
M8 x 1.25| 1.25   | 6.47       | 0.812      | 812      | Muy común
M10 x 1.5| 1.5    | 8.16       | 0.975      | 975      | Muy común
M12 x 1.75|1.75   | 9.61       | 1.138      | 1138     | Común
M14 x 2.0| 2.0    | 11.19      | 1.300      | 1300     | Común
M16 x 2.0| 2.0    | 13.19      | 1.300      | 1300     | Muy común
M18 x 2.5| 2.5    | 14.87      | 1.625      | 1625     | Industrial
M20 x 2.5| 2.5    | 16.87      | 1.625      | 1625     | Muy común
M22 x 2.5| 2.5    | 18.87      | 1.625      | 1625     | Industrial
M24 x 3.0| 3.0    | 20.31      | 1.949      | 1949     | Industrial
M27 x 3.0| 3.0    | 23.31      | 1.949      | 1949     | Industrial
M30 x 3.5| 3.5    | 25.43      | 2.275      | 2275     | Industrial
M33 x 3.5| 3.5    | 28.43      | 2.275      | 2275     | Industrial
M36 x 4.0| 4.0    | 30.87      | 2.598      | 2598     | Industrial

================================================================================
ROSCAS MÉTRICAS DE PASO FINO (Fine Pitch) – Más precisión
================================================================================

Rosca    | Paso   | Diam.Fondo | Altura Fil | Q Micras | Notas
---------|--------|------------|------------|----------|------------------
M8 x 1.0 | 1.0    | 6.77       | 0.650      | 650      | Mayor precisión
M10 x 1.25|1.25   | 8.46       | 0.812      | 812      | Mayor precisión
M12 x 1.25|1.25   | 10.46      | 0.812      | 812      | Mayor precisión
M14 x 1.5| 1.5    | 12.16      | 0.975      | 975      | Mayor precisión
M16 x 1.5| 1.5    | 14.16      | 0.975      | 975      | Mayor precisión
M18 x 1.5| 1.5    | 16.16      | 0.975      | 975      | Mayor precisión
M20 x 1.5| 1.5    | 18.16      | 0.975      | 975      | Mayor precisión
M22 x 1.5| 1.5    | 20.16      | 0.975      | 975      | Mayor precisión
M24 x 2.0| 2.0    | 21.59      | 1.300      | 1300     | Mayor precisión
M27 x 2.0| 2.0    | 24.59      | 1.300      | 1300     | Mayor precisión
M30 x 2.0| 2.0    | 27.59      | 1.300      | 1300     | Mayor precisión

================================================================================
ROSCAS MÉTRICAS DE PASO EXTRA FINO (Extra Fine Pitch) – Máxima precisión
================================================================================

Rosca    | Paso   | Diam.Fondo | Altura Fil | Q Micras | Notas
---------|--------|------------|------------|----------|------------------
M10 x 1.0| 1.0    | 8.77       | 0.650      | 650      | Máxima precisión
M12 x 1.0| 1.0    | 10.77      | 0.650      | 650      | Máxima precisión
M14 x 1.25|1.25   | 12.46      | 0.812      | 812      | Máxima precisión
M16 x 1.25|1.25   | 14.46      | 0.812      | 812      | Máxima precisión
M18 x 1.25|1.25   | 16.46      | 0.812      | 812      | Máxima precisión
M20 x 1.25|1.25   | 18.46      | 0.812      | 812      | Máxima precisión

================================================================================
GUÍA RÁPIDA – USOS COMUNES EN TORNO CNC
================================================================================

PEQUEÑAS PIEZAS (Electrónica, joyería, precisión):
M3, M4, M5, M6 con pasos finos
Ejemplo: M5 x 0.75

PIEZAS MEDIANAS (Automotriz, industrial estándar):
M8 x 1.25, M10 x 1.5, M12 x 1.75, M14 x 2.0
Ejemplo: M12 x 1.75

PIEZAS GRANDES (Maquinaria pesada, industrial):
M16 x 2.0, M20 x 2.5, M24 x 3.0
Ejemplo: M20 x 2.5

MÁXIMA PRECISIÓN (Tolerancias estrictas, vibración):
Cualquier rosca con paso fino (MF)
Ejemplo: M16 x 1.5 (en lugar de M16 x 2.0)

RESISTENCIA MÁXIMA (Tuercas, pernos críticos):
Pasos más grandes para misma rosca
Ejemplo: M14 x 2.0 (en lugar de M14 x 1.5)

================================================================================
CÓMO USAR ESTA TABLA EN G76
================================================================================

Paso 1: Identifica tu rosca en la tabla
Busca en orden: Paso Normal → Paso Fino → Paso Extra Fino

Paso 2: Anota tres datos
- Diámetro fondo (columna "Diam.Fondo") → Para parámetro X en G76
- Paso (columna "Paso") → Para parámetro F en G76
- Q Micras (columna "Q Micras") → Referencia para profundidad de corte

Paso 3: Programa G76

Primera línea (siempre igual para métricas triangulares):
G76 P020060 Q50 R50

Segunda línea (cambia según la rosca):
G76 X[Diam.Fondo] Z[Longitud] R0 Q200 F[Paso]

Ejemplo: M20 x 2.5
De tabla: Diam.Fondo = 16.87, Paso = 2.5

```cnc
G76 P020060 Q50 R50
G76 X16.87 Z-35 R0 Q200 F2.5
      ↑ (de tabla)
```

================================================================================
VALORES POR DEFECTO PARA G76 (Roscas triangulares métricas)
================================================================================

Primera línea: SIEMPRE IGUAL
G76 P020060 Q50 R50

Significado:
P020060:
  02 = 2 pasadas de acabado (estándar)
  00 = sin chaflán (sin ángulo de salida)
  60 = ángulo 60° (estándar métrico triangular)

Q50 = Mínimo volumen de corte = 50 micras
R50 = Sobrematerial de acabado = 50 micras

Segunda línea: CAMBIA según rosca
G76 X[Diam.Fondo] Z[Longitud] R0 Q200 F[Paso]

X = Diámetro fondo (DE LA TABLA) en milímetros
Z = Longitud donde termina rosca (del plano) en milímetros, negativo
R0 = Rosca recta (0 grados, para 99% de casos)
Q200 = Profundidad máxima = 0.2 mm (200 micras)
F = Paso exacto (DE LA TABLA) en milímetros

================================================================================
ERRORES COMUNES – EVITAR
================================================================================

❌ INCORRECTO: Usar fórmulas simplificadas para calcular diámetro fondo
✅ CORRECTO: Usar valores de esta tabla ISO 965

❌ INCORRECTO: Confundir "Altura filete" con "Diámetro fondo"
   - Altura filete: Alto del hilo (para referencia)
   - Diámetro fondo: Donde llega la herramienta (para X en G76)

✅ CORRECTO: Diámetro fondo es lo que va en X

❌ INCORRECTO: Usar Q Micras como profundidad de corte
✅ CORRECTO: Q200 (0.2 mm) es profundidad máxima estándar

❌ INCORRECTO: Olvidar que Z debe ser NEGATIVO
   Z-25 (correcto), Z25 (incorrecto)

❌ INCORRECTO: Dejar sin desahogo para escalones
✅ CORRECTO: Si rosca termina a 30 mm y hay escalón, programa Z-28 (2 mm desahogo)

================================================================================
FACTORES A CONSIDERAR AL ELEGIR PASO
================================================================================

PASO NORMAL (Grueso) → Cuando:
- Rosca de uso general
- Resistencia importante
- Material blando (aluminio, latón)
- Velocidad normal de giro

PASO FINO → Cuando:
- Máxima precisión requerida
- Aplicación automotriz/aeronáutica
- Resistencia a vibración
- Espacio limitado en diámetro
- Material acero duro

PASO EXTRA FINO → Cuando:
- Tolerancias muy estrictas
- Ajustes finos
- Aplicaciones de laboratorio/precisión

================================================================================
REFERENCIAS Y NORMATIVA
================================================================================

Todas estas tablas están basadas en:
✓ ISO 965-1:2013 (Roscas métricas ISO - Tolerancias y dimensiones)
✓ ISO 68-1 (Geometría básica de roscas)
✓ ISO 261 (Sistema de designación)
✓ DIN 13 (Compatibilidad con normas alemanas)
✓ Machining Doctor (Base de datos técnica verificada)

================================================================================
DIFERENCIA ENTRE CÁLCULO vs TABLA ISO
================================================================================

Ejemplo M20 x 2.5:

MÉTODO INCORRECTO (Fórmula simplificada):
H = 0.6495 × 2.5 = 1.62 mm
Df = 20 - (2 × 1.62) = 16.76 mm

MÉTODO CORRECTO (Tabla ISO):
Diámetro fondo = 16.87 mm (de tabla)

DIFERENCIA: 0.11 mm (puede parecer pequeña pero afecta ajuste)

Ejemplo M30 x 3.5:

MÉTODO INCORRECTO:
H = 0.6495 × 3.5 = 2.27 mm
Df = 30 - (2 × 2.27) = 25.46 mm

MÉTODO CORRECTO (Tabla ISO):
Diámetro fondo = 25.43 mm (de tabla)

DIFERENCIA: 0.03 mm (casi correcto, pero no es lo mismo)

CONCLUSIÓN:
Usa la tabla. Siempre. Sin excepciones.
Los cálculos pueden funcionar en simulación, pero en máquina real difieren.

================================================================================
TABLA RESUMIDA PARA COPIAR Y USAR RÁPIDO
================================================================================

Para las roscas MÁS USADAS en CNC:

M6 x 1.0:   Df=4.77   F=1.0
M8 x 1.25:  Df=6.47   F=1.25
M10 x 1.5:  Df=8.16   F=1.5
M12 x 1.75: Df=9.61   F=1.75
M14 x 2.0:  Df=11.19  F=2.0
M16 x 2.0:  Df=13.19  F=2.0
M20 x 2.5:  Df=16.87  F=2.5
M24 x 3.0:  Df=20.31  F=3.0
M30 x 3.5:  Df=25.43  F=3.5

Mantén esta lista a mano en el taller.

--------

<img width="1204" height="1600" alt="image" src="https://github.com/user-attachments/assets/188520eb-cf2f-48af-bbd0-0d0bc8954671" />
