# Encontrar clientes y socios comerciales

**10 clientes potenciales · 5 socios comerciales · Una estrategia para cada organización**

Skill de prospección comercial que transforma el contexto de tu empresa en una lista priorizada de oportunidades, respaldadas por fuentes públicas y acompañadas de mensajes personalizados.

## Qué obtienes

En cada ronda, la skill prepara dos listas: diez posibles compradores y cinco posibles socios comerciales. Para cada organización incluye:

- **Encaje comercial:** evidencia de por qué puede ser relevante para tu empresa.
- **Oportunidad propuesta:** una solución o un modelo de colaboración, con las hipótesis claramente identificadas.
- **Contacto verificado:** rol recomendado y canal institucional público con su enlace.
- **Mensaje personalizado:** una apertura pertinente, una pregunta de diagnóstico y una invitación a conversar.
- **Siguiente paso:** una acción concreta y una propuesta de seguimiento.

Las listas se ordenan por prioridad y se incorporan a un registro reutilizable por proyecto. Los mensajes se entregan como borradores; su envío requiere una petición expresa.

## Instalación

Instala la skill desde el [repositorio en GitHub](https://github.com/iamFear/skill-encontrar-clientes):

```sh
npx skills add iamFear/skill-encontrar-clientes --skill clientes-encontrar
```

También puedes proporcionar el archivo [`SKILL.md`](skills/clientes-encontrar/SKILL.md) como instrucciones en un entorno que permita cargarlas manualmente.

## Cómo usarla

Comparte el sitio web de tu empresa, sus documentos comerciales o el contexto del proyecto. Puedes indicar ubicación, sector, tipo de cliente y criterios de selección.

**Buscar clientes y socios en un mercado concreto**

> Usa la skill clientes-encontrar para investigar clientes y socios de mi empresa en Bogotá. Prioriza el sector hotelero y utiliza el contexto del proyecto.

**Continuar una búsqueda anterior**

> Prepara una nueva ronda de clientes y socios. Consulta el registro existente, evita repetir organizaciones y considera las correcciones que hice a los mensajes anteriores.

**Definir el tipo de alianza**

> Busca clientes potenciales y socios que puedan distribuir nuestros servicios en Medellín. Para los socios, prioriza organizaciones con una oferta complementaria y explica qué ganaría cada parte.

Si el contexto disponible no permite identificar la empresa y su oferta, la skill solicita esa información antes de comenzar.

## Cómo investiga

1. **Comprende la empresa.** Revisa la oferta, los segmentos atendidos, el portafolio y el mercado geográfico.
2. **Busca y verifica.** Prioriza fuentes oficiales y comprueba los canales públicos de contacto.
3. **Evalúa el encaje.** Distingue posibles compradores de socios y separa los hechos de las hipótesis comerciales.
4. **Prepara el acercamiento.** Propone un mensaje y un siguiente paso específicos para cada organización.
5. **Conserva el historial.** Añade la nueva ronda al registro y utiliza las correcciones del usuario para ajustar búsquedas posteriores.

## Registro de oportunidades

La skill mantiene un registro titulado `Leads — <nombre de la empresa>`, con clientes y socios separados. Incluye fuentes, fechas de consulta, prioridad, oportunidad, canal de contacto, mensaje, siguiente paso y estado.

| Recursos disponibles | Formato del registro |
| --- | --- |
| Google Sheets conectado y con permisos de edición | Una hoja de cálculo con pestañas de clientes y socios |
| Escritura de archivos y generación de Excel | Un archivo `.xlsx` dentro de `leads/` |
| Escritura de archivos de texto | Dos archivos CSV UTF-8, uno para clientes y otro para socios |
| Sin acceso a hojas ni escritura de archivos | Tablas en la conversación para guardar manualmente |

El índice `leads/clientes-encontrar.json` conserva la ubicación del registro y las preferencias relevantes. En cada ronda se consulta el historial disponible para evitar duplicados. Las oportunidades comienzan con el estado `Sin contactar`.

## Compatibilidad y requisitos

Las instrucciones son independientes del proveedor y del modelo. Están escritas en formato `SKILL.md` para agentes que admitan skills o instrucciones personalizadas.

Para completar el flujo, el agente necesita:

- Acceso al contexto de la empresa: documentos, sitio web o información proporcionada por el usuario.
- Búsqueda web o navegación para consultar fuentes actuales.
- Acceso a Google Sheets o capacidad de guardar archivos para mantener el registro automáticamente.

La skill utiliza las herramientas disponibles en cada entorno; no incluye conectores. Cuando faltan herramientas o fuentes, comunica la limitación y entrega únicamente lo que puede respaldar. Si no hay suficientes organizaciones verificables, indica cuántas faltan en lugar de completar la lista con datos inventados.

## Criterios de calidad

- Fuentes enlazadas y fechas de consulta para respaldar la investigación.
- Evidencia confirmada separada de las hipótesis de oportunidad.
- Canales de contacto públicos y pertinentes para fines profesionales.
- Sin nombres de decisores, correos, resultados o necesidades internas inventados.
- Sin organizaciones repetidas entre clientes y socios ni en rondas previas cuando el historial está disponible.
- Sin presentar una alianza propuesta como una relación existente.

## Estructura del repositorio

```text
.
├── README.md
├── .gitignore
└── skills/
    └── clientes-encontrar/
        └── SKILL.md
```

Los registros de cada empresa se generan al usar la skill. La carpeta `leads/` está excluida mediante `.gitignore` para mantener los datos comerciales fuera del repositorio.
