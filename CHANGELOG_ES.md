
# 0.6.78+84 Hotfix

- Android release

# 0.6.77+81 Hotfix

- Se corrigió un problema al abrir un archivo, por causa de un error visual la librería de flutter nativa cerraba la app

# 0.6.77+80 Hotfix

- Traducción de textos.
- Soporte para "Abrir con" en Androiid

# 0.6.77+79 Hotfix

- Corrección de valores al escanear o pegar una oferta

# 0.6.77+78

- Implementación de ofertas de XCH y Cat´s, ahora podrá crear tus ofertas, compartirlas por cualquier medio y subirlas a los DEX's existentes, al momento está habilitada la subida a Hashgreen y Dexie, próximamente se habilitarán más.
- Se habilitó un botón para poder pegar las ofertas.
- Ahora se puede escanear la oferta desde Dexie.
- Ahora Ozone es una app con la que puedes abrir los archivos .offer en Android, próximamente estará disponible en iOS.
- Detección automática sobre el estado de las ofertas, si las monedas son gastadas desde otra wallet, la oferta se marcará como cancelada.
- Mejoras de rendimiento en la interfaz.
- Mejora de tiempo al agregar cats, ahora se hace de una forma más veloz, pero durante la sincronización de cats es posible que se note cierto lag en la interfaz.
- Ahora ya no se para la sincronización ni generación de wallets al minimizar Ozone, esto para facilitar la generación de direcciones y evitar problemas de rendimiento al regresar a la aplicación, si no desea que Ozone consuma recursos debe cerrarla completamente.
- Mejoras a la hora de escanear las transacciones activas, ahora solo se escanean cada vez que haya una altura de bloque nueva, esto reduce significativamente el consumo de recursos de la aplicación.
- Mejoras al calcular en las direcciones para recibir el "cambio", ahora se usará siempre la dirección siguiente a la activa, si no existiera, se usará la anterior, de esta forma, si la wallet activa es la m/12381/8444/2/20 la dirección de cambio será la m/12381/8444/2/21, sino existe, se usará la anterior m/12381/8444/2/19
- Se ha bloqueado la interfaz para que solo se muestre de forma vertical, ahora si rota el dispositivo Ozone permanecerá vertical para evitar fallos en la interfáz

# 0.6.76+77 HotFix

- Primera liberación de las ofertas con CAT´s y XCH, ahora se puede crear, aceptar y enviar las ofertas a los diferntes DEX configurados

# 0.6.75+76 HotFix

- Corrección a migración CAT2's, en algunos dispositivos no se borraban los tokens CAT1, ahora se realiza un reinicio mas drastico para garantizar que la migración se realice de forma correcta.

# 0.6.75+75

- Migración de los CAT's Versión 2, se ha actualizado el programa de ChiaLisp encargado de realizar las transacciones de este tipo, además, se hicieron cambios en la librería encargada de realizar la transacción con CAT para soportar el nuevo Estándar.
- Se hicieron mejoras a la pantalla de transparencia de cara a la actualización, por último, se programó un reinicio de la sincronización para crear las nuevas direcciones para sincronizar los CAT's
- Ahora se muestra la derivación que corresponde en la pantalla de recibir, esto para ser más transparente con la cantidad de derivaciones usadas en ese momento, por ahora son 150 que se aumentarán en versiones posteriores.
- Se corrigió un bug que impedía que la dirección seleccionada para recibir se mantuviera seleccionada, anteriormente se perdía la configuración, ahora la dirección seleccionada queda guardada permanentemente.
- Se hicieron mejoras para mejorar la migración de bases de datos antiguas, ahora, si no se tienen derivaciones y no se esta conectado al WebSocket, se mostraran en que estado esta la creación de dichas derivaciones para que el usuario sea consciente que se está realizando un proceso de "resincronización"

# 0.6.73+73

- En actualizaciones anteriores se removió Catkchi como token por defecto con la intención de mejorar el rendimiento en la primera apertura, ahora con el uso de librerías nativas para la derivación de claves, este tiempo ya no es importante y ha sido agregado nuevamente como parte del compromiso y agradecimiento a la comunidad por el apoyo que han brindado.
- Ahora algunas funciones serán desactivadas si no se detecta una conección a internet, las funciones son: envío de transacciones y  consulta de Staking en Catkchi
- Soporte universal para bases de datos antiguas, muchos usuarios tuvieron problemas al actualizar Ozone debido a los modelos incompatibles, esto les hacía imposible volver a entrar a la wallet, para ello, ahora se ha creado un mecanismo que reinicia las "cajas" que contienen modelos incompatibles, la única caja que no cambiará su estructura y por lo tanto no se borrara en ningún momento, es la caja "seed" esto significa, que las 24 palabras nunca se perderán. En resumen, si el listado de derivaciones no es compatible, será eliminado y vuelto a crear, de esta forma garantizamos que el usuario pueda seguir actualizando la aplicación sin miedo de perder acceso a sus datos, los datos de sincronización perdidos serán recuperados con los mecanismos que ya se tienen.

# 0.6.71+72

- Se cambio el texto mostrado en el emcabezado de transparencia para ser mas descriptivo.

# 0.6.71+71

- Se corrigieron errores al momento de cambiar de seed.
- Se cambió el nombre de 'compras' a 'Staking' en la extensión de Catkchi
- Se agregó la pantalla de transparencia de Catkchi, ahora puedes ver un listado de wallets donde encontrarás los montos en frío, caliente y a quemarse que tenemos en nuestra potestad

- Liberación de recursos al cambiar de seed o cerrar la app, ahora al ser necesario, se puede hacer una liberación de recursos en el servidor para dejar de sincronizar una wallet anterior, esto mejora el rendimiento y evita fallos en la sincronización.

# 0.6.7+70

- Corrección a migración de base de datos desde la versión 55, que es la versión estable publicada en las tiendas, se hicieron ajustes para que no se congele al ingresar la contraseña y encontrar modelos incompatibles.

# 0.6.7+67

- Corrección a la autenticación por huella en Android, en algunos dispositivos la autenticación por huella fallaba, esto se corrigió cambiando el tema usado en el entorno nativo de Android.
- Se corrigieron algunos problemas de sincronización con WebSocket, ahora el reporte de altura  no se hace por bloques, si 100 dicciones se encuentran en la altura 150, se mandan esas 100 direcciones y se procesan como si fuese una, esto genera una sola actualización de pantalla que mejora el rendimiento.
- Se corrigió un lag visual en la pantalla de tokens, esto se debía a que por cada token se calculaba el color primario del icono del token, ahora se usa un solo color para todos.
- Se corrigió un lag visual que existían en la pantalla de transacciones, esto se logró cambiando el bucle que se encarga de procesar las transacciones entrantes, debido a que ahora gracias a la sincronización por WebSocket, solo existe un medio por el que se registran nuevas coins, basta con agregar un listener a nuevas coins y procesarlas por si existen nuevas transacciones.

# 0.6.3+60

- Se corrigieron problemas con lag en la interfaz del usuario, se cambió la forma en que se actualiza la pantalla, se hicieron ajustes para solo actualizar las partes de la pantalla que corresponde y hacer menos actualizaciones de pantalla cuando no es necesario.
- Se implementó una librería nativa de BLS que permite un mejor rendimiento a la hora de realizar derivaciones, en un futuro puede también usarse para realizar firmas y calcular hashes, pero falta que ver si la diferencia de rendimiento es lo suficientemente importante para hacer estos cambios

# 0.6.1+58

- Se habilitó la autenticación por huella en Android, anteriormente había sido desactivada porque fallaba en algunos dispositivos.

# 0.6.0+56

- Se agregó una nueva forma de sincronizar la wallet, ahora se hace mediante un WebSocket, esto significa, que la aplicación abre una comunicación con el servidor y simplemente queda a la espera de actualizaciones desde el servidor, si existe un nuevo bloque, se procede a actualizar. Esto es muy importante en el rendimiento, porque la aplicación no realiza continuas peticiones al servidor para sincronizar, sino que envía el paquete de direcciones y solo queda a espera de nuevos cambios.

# 0.5.55+55

- Se cambio el símbolo "%" por "APY" en la pantalla de Staking

# 0.5.54+54

- Mejora en la sincronización de las wallets, se incrementó el tamaño de direcciones que se envía a sincronización por petición

# 0.5.53+53

- Se corrigió el historial de Staking de Catkchi

# 0.5.52+52

- Se agregó la extensión de Catkchi, en esta se puede realizar Staking de Catkchi.
- Se hicieron mejoras en la sincronización de la wallet.

# 0.5.50+50

- Se removió una dirección usada en modo debug

# 0.5.49+49

- Corrección en sincronización de wallet, ahora, la sincronización se realiza de forma individual, es decir, se tiene una altura de sincronización para cada token en cada derivación

# 0.5.48+48

- Se corrigió la forma en que se sincroniza la wallet debido a que el método anterior daba lugar a fallos

# 0.5.47

- Se corrigió la dirección de quien envía la transacción de tipo CAT's, en la versión anterior no se realizó de forma correcta
- Se corrigieron los datos mostrados en las transacciones salientes.

# 0.5.45

- Se corrigió la dirección de quien envía una Transacción de CAT's, en versiones anteriores se mostraba un valor erróneo

# 0.5.44

- Mejoras de rendimiento al realizar la sincronización de las direcciones.
- Corrección de pequeños errores.
- Se actualizó la versión de la API, para usar una nueva estructura en el servidor.
- Se actualizó las librerías para mejorar aspectos de rendimiento y organización de código.

# 0.5.43

- Se corrigió un bug que elimina todos los tokens anteriormente seleccionados si se presiona el boton de atras cuando aun no habian cargado el listado de tokens desde el servidor

# 0.5.42

- Se habilitó la posibilidad de autorelleno la contraseña, esto para hacer uso de herramientas de terceros que permiten la gestión de contraseñas
- Se corrigió el mensaje de confirmación mostrado cuando se establece la contraseña o el pin
- Se corrigió un bug visual cuando se solicitaba la contraseña.

# 0.5.41

- Primera beta pública compilada en iOS

# 0.5.40

- Primera beta pública
