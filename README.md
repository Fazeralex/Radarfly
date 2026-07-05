# Radarfly

**Radar de tráfico aéreo en tiempo real, en un solo archivo HTML.**

Muestra los aviones que sobrevuelan tu zona sobre un *scope* de radar clásico (con barrido de fósforo) o sobre un mapa real, clasifica el tráfico en **salidas / llegadas / en ruta** respecto al aeropuerto de Gran Canaria (GCLP), y te avisa con sonido y voz cuando algo pasa cerca. Pensado para dejar una tablet vieja colgada en la pared como radar-cuadro.

**🔗 Demo:** https://fazeralex.github.io/Radarfly/

Sin instalación, sin cuentas y sin API keys: solo un archivo `index.html` que consume datos abiertos de redes ADS-B comunitarias.

## Características

- **Dos vistas**: scope de radar clásico (anillos de distancia, barrido con persistencia de fósforo, aviones orientados según su rumbo real) y mapa (Leaflet + OpenStreetMap) con el aeropuerto y tu círculo de alcance.
- **Salidas / llegadas / en ruta**, deducido en vivo de la altitud, el régimen de ascenso/descenso y la cercanía a GCLP. Con colores, contadores y filtros.
- **Ficha de cada avión** al tocarlo: aerolínea, ruta (origen → destino), matrícula, tipo, altitud, velocidad, rumbo, régimen vertical, squawk y distancias.
- **Lectura por voz** en español de los datos del avión seleccionado (Web Speech API).
- **Alertas**: pitido al aparecer un contacto nuevo y **zona de alerta configurable** (aviso sonoro + voz cuando un avión entra a menos de X km de ti).
- **Estelas** con las últimas posiciones de cada avión.
- **Fusión de redes**: consulta varias redes ADS-B a la vez y combina los resultados sin duplicados.
- **25 temas** de color y **modo noche automático** (calcula el atardecer/amanecer de tu posición y cambia solo a un tema rojo de instrumentación nocturna).
- **Modo cuadro**: pantalla completa + Wake Lock para que la tablet no se apague.
- **Ubicación flexible**: GPS, coordenadas a mano, o mantener pulsado un punto del mapa.
- Alcance ajustable de 25 a 300 km. Los ajustes se recuerdan entre sesiones.

## Uso

1. Abre la web (o descarga `index.html` y ábrelo en cualquier navegador moderno).
2. Pulsa **◎ UBÍCAME** para fijar tu posición (o mantén pulsado un punto en la vista MAPA).
3. Ajusta el **ALCANCE** y, si quieres avisos de cercanía, elige un radio en **ALERTA**.
4. Toca cualquier avión (en el scope, el mapa o la lista) para ver su ficha y oírla.
5. Para dejarlo de radar-cuadro en una tablet: **⛶ CUADRO** (pantalla completa + pantalla siempre encendida).

> **Nota sobre el GPS:** la geolocalización solo funciona si la página se sirve por HTTPS (como en GitHub Pages). Si abres el archivo directamente desde el gestor de archivos (`file://`), el navegador la bloquea sin preguntar; usa entonces la ubicación manual.

## Datos

Los datos de vuelo provienen de redes ADS-B comunitarias, agregadas por receptores de voluntarios de todo el mundo:

- [adsb.lol](https://adsb.lol) (posiciones y base de rutas)
- [airplanes.live](https://airplanes.live)
- [adsb.one](https://adsb.one)
- [adsb.fi](https://adsb.fi)
- [adsbdb](https://www.adsbdb.com) (rutas, como reserva)

Gracias a todas ellas por ofrecer datos abiertos. Su uso es **personal y no comercial**, conforme a las condiciones de cada red. La cobertura depende de los receptores voluntarios de la zona: en áreas con pocos *feeders* (como Canarias) puede haber menos aviones visibles que en rastreadores comerciales con datos por satélite. ¿La solución de verdad? Montar tu propio receptor con un RTL-SDR y alimentar a estas redes. 😉

La clasificación de salidas/llegadas es una **deducción** a partir de los datos en vivo, no información oficial del aeropuerto.

## Créditos

- Inspirado en los proyectos de radar ADS-B para ESP32 (CYD) de la comunidad maker.
- Mapa: [Leaflet](https://leafletjs.com) + [OpenStreetMap](https://www.openstreetmap.org/copyright).


## Licencia

[MIT](LICENSE) — úsalo, modifícalo y compártelo libremente.
