**Primer punto con el que me encuentro**

El entorno virtual, importante crearlo.

En el reto piden que trabajemos con la versión 3.10 de Python, me imagino para que así todos tengamos la misma versión y evitemos problemas.

Me pregunto:

¿Lo de crear un entorno virtual de que me sirve? ¿Qué consecuencias tiene para el ordenador? Como accedo a él si es virtual? ¿Donde se aloja?

¡Buena pregunta, Iván!

Un entorno virtual en Python es una herramienta que te permite crear un ambiente aislado para tu proyecto, donde puedes instalar las versiones específicas de las librerías que necesites, sin que afecten al resto de proyectos o al sistema global de Python en tu ordenador.

¿Para qué sirve crear un entorno virtual?

•   Aislamiento de Dependencias:

•   Cada proyecto puede tener sus propias librerías y versiones, evitando conflictos entre proyectos.

•   Si un proyecto necesita pandas 1.3 y otro pandas 1.5, los entornos virtuales permiten que ambos proyectos funcionen correctamente en el mismo ordenador.

•   Reproducibilidad:

•   Facilita compartir tu proyecto con otros, ya que pueden instalar exactamente las mismas dependencias que tú usaste.

•   Mejora la estabilidad del proyecto a largo plazo.

•   Seguridad y Organización:

•   Evita modificar el entorno global de Python, reduciendo el riesgo de causar problemas en otros proyectos o aplicaciones del sistema.

  

¿Qué consecuencias tiene para el ordenador?

  

•   Impacto Mínimo:

•   El entorno virtual se aloja en una carpeta dentro de tu proyecto y no afecta al sistema operativo.

•   No modifica variables de entorno globales ni registros del sistema.

•   Uso de Espacio en Disco:

•   Ocupa espacio en tu disco duro, pero generalmente es poco, ya que solo contiene las librerías necesarias para tu proyecto.

  

¿Cómo accedo a él si es virtual?

  

•   Activación del Entorno Virtual:

•   Desde la terminal o línea de comandos, debes “activar” el entorno virtual para utilizarlo.

•   En Windows:

  

  

venv\Scripts\activate

  

•   En macOS/Linux:

  

`source venv/bin/activate`

  

•   Indicador de Activación:

•   Una vez activado, verás que el nombre del entorno (por ejemplo, (venv)) aparece al inicio de tu línea de comandos.

(venv) C:\ruta\de\tu\proyecto>

  

•   Uso en VS Code:

•   Al abrir un proyecto en VS Code, puedes seleccionar el intérprete de Python del entorno virtual para que el editor lo utilice.

  

  

¿Dónde se aloja?

  

•   Dentro de tu Proyecto:

•   El entorno virtual se crea en una carpeta dentro de tu proyecto, comúnmente llamada venv o env.

•   Estructura típica:

  

  

tu_proyecto/

├── venv/               # Carpeta del entorno virtual

│   ├── bin/ (o Scripts/)  # Ejecutables de Python y scripts

│   └── lib/               # Librerías instaladas

├── src/                # Código fuente de tu proyecto

├── data/               # Datos del proyecto

└── requirements.txt    # Archivo con las dependencias

  

Pasos para Crear y Usar un Entorno Virtual

  

1.  Crear el Entorno Virtual:

•   Abre la terminal y navega hasta la carpeta raíz de tu proyecto:

  

  

cd ruta/de/tu/proyecto

  

•   Ejecuta el siguiente comando para crear el entorno virtual llamado venv:

  

  

python3.10 -m venv venv

  

•   Nota: Asegúrate de que python3.10 está instalado en tu sistema. Si no, puedes usar python o la versión que corresponda.

  

2.  Activar el Entorno Virtual:

•   En Windows:

  

  

venv\Scripts\activate

  

•   En macOS/Linux:

  

  

source venv/bin/activate

  

•   Verificar la Activación:

•   El prompt de tu terminal debería cambiar para indicar que el entorno virtual está activo.

  

3.  Instalar Dependencias en el Entorno Virtual:

•   Con el entorno virtual activo, instala las librerías necesarias:

  

  

pip install -r requirements.txt

  

•   Esto instalará las librerías especificadas en requirements.txt dentro del entorno virtual.

  

4.  Usar el Entorno Virtual en VS Code:

•   Seleccionar el Intérprete de Python:

•   En VS Code, presiona Ctrl+Shift+P (o Cmd+Shift+P en macOS) para abrir la paleta de comandos.

•   Escribe Python: Select Interpreter y selecciona el intérprete que está dentro de tu entorno virtual, que suele estar en venv/bin/python o venv/Scripts/python.exe.

  

  

Ventajas de Usar Entornos Virtuales

  

•   Evita Conflictos:

•   Diferentes proyectos pueden requerir distintas versiones de librerías. Los entornos virtuales permiten que cada proyecto tenga su propio conjunto de dependencias.

•   Fácil Mantenimiento:

•   Si algo sale mal en un proyecto, puedes eliminar el entorno virtual y crear uno nuevo sin afectar al sistema global.

•   Colaboración Efectiva:

•   Otros desarrolladores pueden recrear fácilmente el entorno exacto en el que trabajas, lo que facilita el trabajo en equipo.

  

  

¿Es Seguro para mi Ordenador?

  

•   Sí, es Seguro:

•   Los entornos virtuales no realizan cambios en el sistema operativo ni en el Python global instalado.

•   Operan completamente dentro de la carpeta de tu proyecto.

  

  

¿Qué Pasa si No Uso un Entorno Virtual?

  

•   Posibles Problemas:

•   Instalar librerías globalmente puede causar conflictos entre proyectos.

•   Actualizar una librería para un proyecto podría romper otro que depende de una versión anterior.

  

  

Resumen

  

•   Un entorno virtual es una herramienta esencial para el desarrollo en Python, especialmente en proyectos profesionales.

•   Te permite trabajar en un ambiente controlado y aislado, asegurando que las dependencias y configuraciones de un proyecto no interfieran con otros.

•   No tiene consecuencias negativas para tu ordenador y es fácil de crear y usar.