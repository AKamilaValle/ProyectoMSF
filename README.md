[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=AKamilaValle/ProyectoMSF)

# Proyecto: Sistema de la nefrona

## Información de la estudiante
Durán Sofía \[22211752]; l22211752@tectijuana.edu.mx
Galindo Belén \[22211755]; l22211755@tectijuana.edu.mx
Sifuentes Anadalí \[22212273]; l22212273@tectijuana.edu.mx
Valle Ana \[22211769]; l22211769@tectijuana.edu.mx

Modelado de Sistemas Fisiológicos

Ingeniería Biomédica

## Docente
Dr. Paul Antonio Valle Trujillo; paul.valle@tectijuana.edu.mx

Departamento de Ingeniería Eléctrica y Electrónica, Tecnológico Nacional de México/IT Tijuana, Blvd. Alberto Limón Padilla s/n, Tijuana, C.P. 22454, B.C., México.

## Descripción de la asignatura

El modelizado de sistemas fisiológicos es una herramienta importante en Ingeniería Biomédica, permite comprender el funcionamiento del cuerpo humano, así como diseñar y evaluar terapias y dispositivos médicos; se define como el proceso de formular modelos matemáticos o computacionales que representan el comportamiento y la interacción de los sistemas biológicos y fisiológicos. Esta asignatura pretende aportar al perfil del Ingeniero Biomédico la capacidad de realizar investigación científica en el área de Biología de Sistemas con la finalidad de dirigir y participar en equipos de trabajo interdisciplinarios en contextos nacionales e internacionales, así como de proporcionar soluciones informáticas para resolver problemas en el campo de la Ingeniería Biomédica con ética profesional; lo anterior al proporcionar al estudiante bases sólidas para modelizar sistemas y diseñar controladores para la solución de problemas en las áreas de atención médica y del sector industrial médico. La construcción de analogías entre circuitos eléctricos y sistemas fisiológicos para la formulación de modelos matemáticos y el diseño de controladores mediante la experimentación in silico brindan herramientas de gran aplicación en el quehacer profesional del Ingeniero Biomédico.

La asignatura de Modelado de Sistemas Fisiológicos forma parte del plan de estudios de la carrera en Ingeniería Biomédica con la siguiente competencia general del curso: Utiliza las propiedades de los circuitos RLC para describir la dinámica de sistemas fisiológicos, obtener modelos matemáticos y aplicar el control clásico, esto con el objetivo de integrar los principios de la Ingeniería de Control, la Electrónica Analógica y las Ciencias de la Computación con la Anatomía y Fisiología del cuerpo humano para proporcionar descripciones cuantitativas y cualitativas de sistemas fisiológicos complejos con el objetivo de modelizar, analizar, controlar, ilustrar y predecir su dinámica tanto en el corto como en el largo plazo.

## Objetivos

1. Calcular la función de transferencia.
2. Determinar el modelo de ecuaciones integro-diferenciales.
3. Calcular el error en estado estacionario y la estabilidad en lazo abierto.
4. Emular y simular la respuesta del circuito en Simulink/Simscape con una señal de impulso.
5. Sintonizar las ganancias de un controlador PID para eliminar el error entre la entrada y la salida del sistema con la nefropatía.
6. Obtener la respuesta en lazo abierto y en lazo cerrado con el controlador PID con la función de transferencia.
7. Diseñar el modelo fisiológico del sistema (control y caso) en BioRender.

## Descripción detallada del sistema

### Sistema Fisiológico: La Nefrona

La nefrona es la unidad funcional básica del riñón, responsable de la filtración de la sangre y la formación de orina. Cada riñón humano contiene aproximadamente 1 millón de nefronas. El proceso de formación de orina involucra tres mecanismos principales: filtración glomerular, reabsorción tubular y secreción tubular.

#### Componentes anatómicos de la nefrona:

1. **Glomérulo**: Red de capilares especializados donde ocurre la filtración de la sangre.
2. **Cápsula de Bowman**: Estructura que rodea el glomérulo y recibe el filtrado.
3. **Túbulo contorneado proximal**: Segmento donde se reabsorbe aproximadamente el 65% del filtrado glomerular.
4. **Asa de Henle**: Estructura en forma de "U" que regula la concentración de la orina.
5. **Túbulo contorneado distal**: Segmento de ajuste fino de la reabsorción.
6. **Conducto colector**: Estructura final donde se concentra la orina antes de su excreción.

#### Proceso de filtración glomerular:

La sangre llega a la nefrona a través de la **arteriola aferente**, ingresando al glomérulo donde es filtrada bajo presión. La presión hidrostática (aproximadamente 55 mmHg) impulsa el plasma sanguíneo a través de las paredes capilares hacia la cápsula de Bowman, formando el **filtrado glomerular**. La sangre filtrada sale del glomérulo por la **arteriola eferente**, mientras que el filtrado continúa su tránsito por los túbulos renales.

### Patología: Nefropatía Diabética

La nefropatía diabética es una complicación crónica de la diabetes mellitus que afecta la función renal. Es la principal causa de enfermedad renal crónica terminal y se caracteriza por cambios progresivos en la estructura y función de la nefrona.

#### Fisiopatología:

1. **Hiperfiltración glomerular inicial**: En las etapas tempranas de la diabetes, el glomérulo experimenta un aumento del flujo sanguíneo y de la tasa de filtración glomerular (20-40% por encima de lo normal). Esto ocurre debido a la vasodilatación de la arteriola aferente y la vasoconstricción relativa de la arteriola eferente, lo que incrementa la presión intraglomerular.

2. **Alteraciones estructurales**:
   - Engrosamiento de la membrana basal glomerular
   - Expansión mesangial
   - Esclerosis glomerular progresiva
   - Acumulación de matriz extracelular

3. **Alteración de la permeabilidad glomerular**: La barrera de filtración pierde su selectividad normal, permitiendo el paso de proteínas (albuminuria), lo cual es un marcador temprano de daño renal.

4. **Fibrosis túbulo-intersticial**: Los túbulos renales experimentan cambios degenerativos con pérdida de su elasticidad y capacidad de reabsorción. Se produce acumulación de tejido fibroso que sustituye al tejido funcional.

5. **Daño vascular**: Las arteriolas sufren hialinosis y esclerosis, aumentando la resistencia al flujo sanguíneo y comprometiendo la perfusión renal.

6. **Reducción progresiva de la función renal**: Con el tiempo, el número de nefronas funcionales disminuye, llevando a una insuficiencia renal progresiva.

### Modelado mediante circuito eléctrico RLC

Para representar la dinámica del sistema renal, se establece una analogía entre las variables fisiológicas y eléctricas:

| Variable Fisiológica | Variable Eléctrica |
|---------------------|-------------------|
| Presión sanguínea/hidrostática | Voltaje (V) |
| Flujo de filtrado glomerular | Corriente eléctrica (I) |
| Resistencia vascular (arteriolas) | Resistencia eléctrica (R) |
| Compliance/distensibilidad | Capacitancia (C) |
| Inercia del flujo sanguíneo | Inductancia (L) |

#### Componentes del circuito:

**R1 - Resistencia de la arteriola aferente**
- Representa la resistencia al flujo sanguíneo que entra al glomérulo
- Controla la presión de filtración glomerular
- **Control (sano)**: R1 = 100 Ω
- **Caso (diabético)**: R1 = 250 Ω

**L - Inductancia del flujo sanguíneo glomerular**
- Representa la inercia de la masa de sangre en los capilares glomerulares
- Modela la oposición al cambio rápido en el flujo
- **Control**: L = 50 mH
- **Caso**: L = 50 mH

**C1 - Compliance glomerular**
- Representa la distensibilidad de los capilares glomerulares y la cápsula de Bowman
- Modela la capacidad de almacenamiento temporal del filtrado
- **Control**: C1 = 100 μF
- **Caso**: C1 = 180 μF

**R2 - Resistencia de la arteriola eferente y sistema tubular**
- Representa la resistencia combinada de la arteriola eferente y la fricción tubular
- Controla la presión de salida del glomérulo y el flujo a través de los túbulos
- **Control**: R2 = 150 Ω
- **Caso**: R2 = 300 Ω

**C2 - Compliance tubular**
- Representa la distensibilidad de los túbulos renales
- Modela la capacidad de almacenamiento y reabsorción tubular
- **Control**: C2 = 200 μF
- **Caso**: C2 = 350 μF

**Descripción funcional:**
- **Ve(t)**: Presión arterial sistémica (entrada del sistema) = 120 V ≈ 120 mmHg
- **R1**: Resistencia de la arteriola aferente
- **L**: Inercia del flujo sanguíneo en capilares glomerulares
- **C1**: Compliance del glomérulo y cápsula de Bowman
- **R2**: Resistencia de la arteriola eferente + resistencia tubular
- **C2**: Compliance del sistema tubular
- **Vs(t)**: Presión en el conducto colector (salida del sistema)

**Orden del sistema**: Tercer orden (1 inductor + 2 capacitores)

**Señal de entrada**: Escalón unitario de amplitud 120 V, representando la presión arterial media que impulsa la filtración glomerular.

Palabras clave: Circuito RLC; Controlador PID; Sistema renal; Nefrona; Nefropatía diabética; Modelo matemático; Simulaciones numéricas; Filtración glomerular.

## Lista de archivos incluidos en el repositorio
1. Cuaderno computacional de MATLAB [.mlx].
2. Modelo de Simulink [.slx].
3. Archivos de Spyder [.py].
4. Imagen con los parámetros del controlador.
5. Imágenes de las simulaciones [.pdf y .png].
6. Evidencia del análisis matemático: función de transferencia, modelo de ecuaciones integro-diferenciales, error en estado estacionario y estabilidad en lazo abierto.

## Referencias
\[1] P. A. Valle, Syllabus para Modelado de Sistemas Fisiológicos, Tecnológico Nacional de México / Instituto Tecnológico de Tijuana, Tijuana, B.C., México, 2025. Permalink: https://biomath.xyz/course/

\[2] L. C. Segovia Cañar, F. D. Carranza López, y D. S. Baño Mora, "Manejo de la nefropatía diabética: Artículo de revisión," LATAM Revista Latinoamericana de Ciencias Sociales y Humanidades, vol. VI, no. 1, pp. 116–127, enero, 2025. doi: 10.56712/latam.v6i1.3314.

\[3] S. Zheng, D. Carugo, A. Mosayyebi, B. Turney, F. Burkhard, D. Lange, D. Obrist, S. Waters, and F. Clavica, "Fluid mechanical modeling of the upper urinary tract," WIREs Mechanisms of Disease, vol. 13, no. 6, art. no. e1523, 2021, doi: 10.1002/wsbm.1523.
