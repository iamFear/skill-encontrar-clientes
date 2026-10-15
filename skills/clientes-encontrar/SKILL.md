---
name: clientes-encontrar
description: Investiga tandas de 10 clientes potenciales y 5 socios comerciales para la empresa del proyecto activo, con estrategias de contacto basadas en fuentes públicas, y conserva los leads en una hoja reutilizable por proyecto. Úsala cuando el usuario pida prospectos, aliados comerciales u oportunidades de crecimiento.
---

# Encontrar clientes y socios comerciales

Entrega en cada ronda **10 clientes potenciales y 5 socios comerciales potenciales**, todos concretos y distintos, con una estrategia de contacto individual. Usa el idioma del usuario y del proyecto. Si el usuario fija sector, ciudad, tipo de cliente, tipo de socio o criterios de selección, respétalos; en ausencia de restricciones, infiere el mercado y los segmentos prioritarios de las fuentes del proyecto activo.

## Compatibilidad y herramientas

Estas instrucciones son independientes del proveedor y del modelo. Usa las herramientas equivalentes disponibles en el agente: búsqueda web o navegador, lectura de documentos y edición de hojas o archivos. No requieren APIs, nombres de herramientas, sintaxis de invocación ni memoria propios de un proveedor.

Si el agente no carga skills automáticamente, el usuario puede proporcionar este documento como instrucciones. La ejecución completa requiere consultar fuentes actuales y guardar el registro. Si no hay acceso web, solicita fuentes actuales al usuario y limita la verificación a lo que realmente puedas consultar; explica qué falta y no presentes prospectos como verificados sin evidencia. Si no puedes completar diez clientes y cinco socios verificados con los recursos disponibles, entrega los verificados e indica cuántos faltan y por qué.

## Contexto de la empresa

Antes de buscar, identifica la empresa asociada al proyecto activo, a la página web, o a los documentos e información que el usuario provea. Revisa las instrucciones del proyecto disponibles (por ejemplo, `AGENTS.md` si existe), documentos comerciales y técnicos, datos estructurados, páginas del sitio web y otras carpetas o indicaciones que el usuario haya aportado. Prioriza las fuentes originales frente a transcripciones o copias. No arrastres datos de empresas o proyectos anteriores salvo que el usuario pida relacionarlos. Si el proyecto no permite identificar la empresa ni su oferta, pide esa información antes de investigar prospectos.

Extrae segmentos atendidos, productos o servicios, casos comparables, mercado geográfico y datos oficiales de contacto. No conviertas fechas de proyectos en fecha de fundación ni supongas que un trabajo histórico sigue vigente. Trata cifras de desempeño, ahorro o retorno como estimaciones condicionadas cuando así lo indiquen las fuentes. No inventes capacidades, precios, resultados ni estado actual de la empresa.

## Investigación y selección

Busca en la web fuentes actuales para identificar prospectos, confirmar que siguen operando y hallar un canal institucional público de contacto. Da preferencia a sitios oficiales de cada organización; complementa con fuentes públicas fiables cuando haga falta. Registra la fecha de consulta y enlaza las fuentes que respaldan cada dato. Una pista comercial o una necesidad técnica inferida debe quedar marcada como hipótesis, nunca como hecho verificado.

Selecciona diez posibles compradores con una razón específica de encaje y una oferta inicial plausible para cada uno. Selecciona además cinco posibles socios que puedan complementar la oferta, acceder a clientes o integrar la empresa en proyectos, con un beneficio plausible para ambas partes. Considera tipos de socio pertinentes al negocio, por ejemplo estudios de arquitectura, constructoras, desarrolladores inmobiliarios, ingenierías, integradores, distribuidores, operadores o asociaciones sectoriales; no los impongas en proyectos donde no encajen. Distingue al socio del comprador: una alianza propuesta no equivale a una venta ni a una relación existente.

Evita repetir organizaciones de tandas anteriores si el historial está disponible y evita incluir la misma organización en ambas listas. Distingue a los clientes que figuran en el portafolio de la empresa; inclúyelos solo si el usuario pide reactivación. Si una organización o su canal no se puede verificar, busca otra antes de completar la tanda. No inventes nombres de decisores, correos, teléfonos, proyectos previstos, relaciones existentes ni problemas internos. Usa contactos personales únicamente si están publicados para fines profesionales pertinentes.

Antes de iniciar una nueva tanda, consulta las modificaciones del usuario a la tanda anterior (resultados, respuestas, textos cambiados y criterios). Ajusta la selección y los mensajes según esa evidencia. Guarda las preferencias relevantes en el registro para poder recuperarlas en otra sesión; no presupongas memoria persistente ni entrenamiento del modelo.

## Registro persistente de leads

Mantén **un solo registro por proyecto activo**, titulado `Leads — <nombre de la empresa>`. Antes de investigar una nueva tanda, busca en el proyecto el archivo `leads/clientes-encontrar.json`, que guarda el ID y enlace de la hoja de Google o la ruta del archivo local. Abre el registro existente, consulta sus organizaciones para evitar duplicados y añade la nueva tanda sin sobrescribir filas anteriores. Si el identificador falta, busca una hoja existente con ese título y comprueba que corresponda a la misma empresa y proyecto antes de crear otra. Guarda el identificador en `leads/clientes-encontrar.json` después de crearla; el título por sí solo no identifica de forma fiable un documento.

Usa esa ruta en cada tanda. Si el usuario ya tiene un índice en otra ubicación, reutilízalo y comunica su ruta. El índice debe guardar la empresa y el proyecto, el tipo de registro, el ID y enlace de la hoja o las rutas de los archivos locales, las preferencias aprendidas y la fecha de actualización. No dependas de recordar estos datos entre sesiones: vuelve a leer el índice.

Cuando Google Sheets esté conectado, crea o reutiliza una hoja de cálculo de Google con ese título. Organiza clientes y socios en pestañas separadas. Incluye como mínimo empresa, ciudad, sector o tipo, prioridad, evidencia y su fuente, oportunidad marcada como hipótesis, solución o modelo de colaboración, rol y canal institucional con enlace, mensaje propuesto, siguiente paso, estado del contacto, fecha de consulta y fecha de incorporación. Deja el estado como `Sin contactar` hasta contar con evidencia de un contacto real. Actualiza filas existentes si se verifica información nueva, conservando el historial cuando sea útil.

Si Google Sheets no está conectado o no permite crear la hoja, crea o reutiliza un archivo local `.xlsx` en `leads/<slug-de-la-empresa>.xlsx` dentro del proyecto, con las mismas pestañas y columnas. Registra esa ruta en `leads/clientes-encontrar.json` y entrega un enlace al archivo. En rondas posteriores usa siempre ese mismo archivo. Cuando vuelva la conexión, importa sus datos a **una sola** hoja de Google, guarda su ID en el registro y continúa allí; comprueba los duplicados antes de agregar filas. No crees una hoja nueva por cada ronda ni afirmes que los datos están en Google Sheets si solo existe el archivo local.

Si no puedes generar `.xlsx`, utiliza dos archivos CSV UTF-8, `leads/<slug-de-la-empresa>-clientes.csv` y `leads/<slug-de-la-empresa>-socios.csv`, con las mismas columnas, y registra ambas rutas en el índice. Si no puedes escribir archivos ni acceder a una hoja, entrega las tablas y el contenido del índice para que el usuario los guarde y los proporcione en la siguiente ronda. Explica que no se han guardado automáticamente y que evitar duplicados entre sesiones requiere recuperar ese historial. Nunca afirmes haber leído o actualizado un registro sin haberlo hecho.

## Estrategia por cliente

Para cada organización incluye:

- Nombre, ciudad, sector y enlace a su fuente oficial.
- Evidencia concreta de encaje, separada de la hipótesis de oportunidad.
- Producto o servicio de la empresa que conviene explorar y por qué; plantea las preguntas de diagnóstico pertinentes antes de prometer resultados.
- Rol al que conviene dirigirse, canal institucional verificado y enlace directo al canal. Si no hay canal verificable, sustitúyela por otro prospecto.
- Enfoque de primer contacto: referencia pertinente del portafolio si existe, mensaje breve y personalizado en el idioma elegido, una pregunta de diagnóstico y una invitación concreta a conversar.
- Siguiente paso y seguimiento razonable si no hay respuesta, sin afirmar que se contactó a nadie.

## Estrategia por socio

Para cada uno de los cinco socios incluye nombre, ubicación, tipo de organización, fuentes oficiales y evidencia de complementariedad. Explica un modelo concreto de colaboración que convenga explorar —por ejemplo, prescripción en el diseño, propuesta conjunta, integración técnica, distribución o acceso a un segmento— y qué podría ganar cada parte. Señala como hipótesis cualquier interés o capacidad de colaboración no confirmados. Identifica el rol adecuado, un canal institucional público verificado, un mensaje breve y personalizado, una pregunta para calificar la alianza, un siguiente paso y un seguimiento razonable. No presentes a un competidor directo como aliado sin explicar la complementariedad comprobada.

Abre con dos listas o tablas separadas, una de diez clientes y otra de cinco socios, ordenadas por prioridad y con una explicación breve del criterio. Después desarrolla las estrategias individuales. Cierra con incertidumbres relevantes y fuentes, y enlaza el registro de leads utilizado. Redacta mensajes listos para adaptar, pero **no los envíes ni cargues datos en sistemas externos distintos del registro de leads solicitado** salvo que el usuario lo pida expresamente.
