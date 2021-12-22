![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/Documentaci%C3%B3n/LogoBytte.png)

# Bytte SDK
# Documento Integración SDK React Native
### CONFIDENCIALIDAD

La información contenida en el presente documento es CONFIDENCIAL, hace parte del secreto comercial e industrial de la empresa e implica transmisión de información cuya propiedad corresponde exclusivamente a BYTTE SAS. En consecuencia, la divulgación o el uso inapropiado de la información aquí contenida por parte del receptor de la misma, implicarán la aplicación de las normas legales pertinentes para su debida protección.

### 1. INTRODUCCIÓN

#### Propósito General del Documento

El presente documento tiene como finalidad dar a conocer el paso a paso de la instalación del SDK provisto por Bytte en una aplicación hibrida generada en React Native.

#### 1.1. Objetivo

El presente documento tiene como objetivo explicar basado en un ejemplo, cómo realizar la integración del SDK Bytte a una aplicación React Native.

#### 1.2. Factores Limitantes

Los factores limitantes para la integración del SDK son:
* El Plugin SDK Bytte, está disponible para plataformas IOS y Android únicamente.
* Se recomiendan cámaras con resolución mayores o iguales a 8 Mega Pixeles para un óptimo rendimiento.
* Se debe verificar la calidad de la cámara, es recomendable utilizar dispositivos con cámara que tengan la característica de “Auto Foco” habilitada.
* El SDK no funciona sobre dispositivos virtuales, únicamente sobre dispositivos físicos IPhone y Android.

### 2. INSTALACIÓN

#### 2.1. Pre requisitos

* General:
    > * NPM (sistema de gestión de paquetes)

* Para la compilación de aplicación en plataforma IOS, se requiere:
    > * XCode 12 o Superior con SDK IOS 12 o superior.

#### 2.2. Instalación Plugin react-native-bytte-bio-lib-ID

#### 2.2.1 Configuración Token

#### 2.2.1.1 MAC

Una vez instalado NPM (sistema de gestión de paquetes). En la ruta por defecto de instalación se debe encontrar el archivo .npmrc, si no se encuentra se debe crear a nivel de usuario.

Una vez detectado el archivo se debe configurar de la siguiente manera.


``` txt
registry=https://byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/registry/ 
                        
always-auth=true

; begin auth token
//byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/registry/:username=BytteTFS
//byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/registry/:_password=(TOKEN)
//byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/registry/:email=npm requires email to be set but doesn't use the value
//byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/:username=BytteTFS
//byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/:_password=(TOKEN)
//byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/:email=npm requires email to be set but doesn't use the value
; end auth token
```

En el espacio (*TOKEN*) se debe ingresar el password enviado por Bytte sas.

#### 2.2.1.2 WINDOWS

Una vez instalado NPM (sistema de gestión de paquetes). Se debe ejecutar el siguiente comando en la terminal.

``` vsts-npm-auth -config .npmrc```

este comando creará un archivo .npmrc en la ruta por defecto C:\Users\USER\\.npmrc

Una vez detectado el archivo se debe configurar de la siguiente manera.

``` txt
registry=https://byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/registry/ 
                        
always-auth=true

; begin auth token
//byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/registry/:username=BytteTFS
//byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/registry/:_password=(TOKEN)
//byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/registry/:email=npm requires email to be set but doesn't use the value
//byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/:username=BytteTFS
//byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/:_password=(TOKEN)
//byttetfs.pkgs.visualstudio.com/c1dcbe70-4508-4f44-bfa8-e50bdbfea41f/_packaging/react-native-bytte-bio-lib-id/npm/:email=npm requires email to be set but doesn't use the value
; end auth token
```

En el espacio (*TOKEN*) se debe ingresar el password enviado por Bytte sas.

#### 2.2.2 Instalación 

`$ npm install react-native-bytte-bio-lib-id`


Una vez instalado el plugin, se debe realizar la consulta a la aplicación para verificar que este quedó correctamente instalado.

#### 2.3. Configuración nativo iOS (XCode)

######   Adicionar la implementación bytte a su proyecto NPM
Para esta implementación se puede generar desde npm integrando de la siguiente forma: 

``` npm install react-native-bytte-bio-lib-id```

Luego de instalar las dependencias npm se ingresa a la carpeta ***ios*** y se ejecuta el comando `pod install`

    $ cd ios
    $ pod install

![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/podinstall.png)

Luego se ingresa al proyecto IOS y en la sección  ***Development Pods*** se busca la carpeta  ***RNBytteBioLibMiiD*** donde se encuentra los archivos correspondientes a la librería. En la carpeta ***Frameworks*** se encuentran los binarios que deben ser embebidos de manera local al proyecto.

![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/framework4.png)

Una vez agregados se valida que se encuentren  ***Embed & sign*** 

![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/framework5.png)

######   Configuración Framework Search Paths

Se obtiene la ruta donde se encuentran los Framework bytte y se configura en Framework Search Paths

Ruta por defecto : ***Ruta_Proyecto***/bytteTest/node_modules/react-native-bytte-bio-lib-miid/ios/Frameworks

![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/framework2.png)

######   Configuración Pod RNBytteBioLib Framework Search Paths

Se obtiene la ruta donde se encuentran los Framework bytte y se configura en ***pod*** ***RNBytteBioLibMiiD*** Framework Search Paths

Ruta por defecto : ***Ruta_Proyecto***/bytteTest/node_modules/react-native-bytte-bio-lib-miid/ios/Frameworks

![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/framework3.png)

###### Licencia captura dactilar

Bytte proporciona el archivo de licencia para captura dactilar. Este archivo debe ser guardado en la raiz del proyecto IOS y embebido como recurso en la aplicación nativa tal como lo muestra la siguiente imagen.

![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/framework6.png)

El nombre del archivo se envía por parámetro ***(namePath)*** en la captura dactilar.


######   Permisos
Los permisos en runtime deben ser solicitados por la app para el uso de bytte es necesario el siguiente:
configurar en el archivo Info.plist para el uso de la ***Cámara***

`Privacy - Camera Usage Description`

# 2.4. Configuración  Android
# Factores Limitantes 
Los factores limitantes para la integración del SDK son:

* Se debe verificar la calidad de la cámara, es recomendable utilizar dispositivos con cámara que tengan la característica de “AutoFoco” y flash.
* Se recomiendan cámaras con resolución mayores o iguales a 5 MegaPixeles frontal y 8 MegaPixeles para un óptimo rendimiento, “mejor cámara mejora las imágenes”.
* El SDK no funciona sobre dispositivos virtuales, únicamente sobre dispositivos físicos.
* No presenta inconveniente para compilaciones Android 30.
* Mínima versión soportada Android 19.
* Esta solución ya trabaja sobre androidX por lo cual si el proyecto no lo soporta se debe migrar para que la captura de los documentos funcionen.


* **Se debe verificar la calidad de la cámara, es recomendable utilizar dispositivos con cámara que tengan la característica de “Auto Foco” habilitada.**
* **Se recomiendan cámaras con resolución mayores o iguales a 8 MegaPixeles para un óptimo rendimiento.**
* **El SDK no funciona sobre dispositivos virtuales, únicamente sobre dispositivos físicos.**
* **Sistemas soportados Android 5.0 o superior gradle 4.1.2 o superior arquitecturas arm  x86,64 bits.**

# Instalación de las librerías 
En el archivo gradle build.gradle  del proyecto adicionaremos la 'URL' que nos entrega Bytte para la descarga de los archivos necesarios, al igual que el usuario y token de acceso.

>Las librerías tiene soporte tanto a 32 como a 64 bit en arm. 



Generamos la siguiente configuración: en el Gradle. build.gradle de android, allprojects/repositories 
username= Usuario de conexión para la descarga de las librerías
password= Token de conexión para la descarga de las librerías
Estos datos son entregados por Bytte son necesarios para la conexión y descarga de las librerías

```gradle
   maven {
                url 'https://byttetfs.pkgs.visualstudio.com/BytteSDKLibrarys-Android/_packaging/SdkBytteV2/maven/v1'
                name 'SdkBytteV2'
                credentials {
                    username ""
                    password ""
                }
            }
```
**Las librerías tiene soporte tanto a 32 como a 64 bit en arm.


#### Licenciamiento para captura de documentos:
Es necesario el nombre de la app o bundleid ej:'com.bytte.casb' con ello se genera un string el cual se pasa por parámetro, para las capturas de documentos funcionen.
Ejm= sRwAAAEcY29tLmJpb21ldHJpYy5ieXR0ZS5jYXNiYXV0aGwvBQWzcDTlsQl3yJ1mesdlcj2sdrMSJvBW52EtPkL73OxXk7gkJpJKpZm4EirHgF41K2IWg23Zct2aD1PvnDidue2a5RxgmOhu5qE78eRU0zFdhlEU1gvgcv6PGgYJHW4VRAyUs2LAaVj6v1Nyh8YXCLpv5ziCGUqV9aQg


#### Para el licenciamiento de Biometría 'huellas'
Se requiere de igualmente el bundle para la generación de la licencia, en este caso se genera un archivo el cual debe ir en la siguiente ruta Android. android/app/src/main/assets.
Y hay pegamos el archivo que entrega bytte para su correcto funcionamiento


## Configuración colores de la pantalla de huellas
>boxes -> Color de borde  del cuadro de la cámara.
>boxes_transparent -> Color del recuadro  entre el header y el footer.
>colorPrimary -> Color del footer y el header. 

    ```  xml
    <color name="boxes">#FF5722</color>
    <color name="boxes_transparent">#FF5722</color>
    <color name="colorPrimary">#FFC107</color>
    <color name="colorPrimaryDark">#FF5722</color>

    ```
## Configuración en español para mensajes huellas
Vamos a la carpeta res/values/strings.xml

``` xml
 <string name="id_searching_left">Buscando dedos izquierdos…</string>
    <string name="id_searching_right">Buscando dedos derechos…</string>




        <string name="id_authentication_retake">INSEGURO VOLVER A TOMAR</string>
        <string name="id_authentication_successful">Autenticado</string>
        <string name="id_authentication_unsuccessful">Autenticación incorrecta</string>
        <string name="id_capture_completed">Captura completada</string>
        <string name="id_captured">Capturado</string>
        <string name="id_capturing">Capturando..</string>
        <string name="id_close">Cerrar</string>
        <string name="id_confirm_exit">Confirmar salida</string>
        <string name="id_continue">SEGUIR</string>
        <string name="id_dshow_again">No me lo muestres de nuevo</string>
        <string name="id_enrollment_completed">INSCRIPCIÓN FINALIZADA</string>
        <string name="id_exit_text">¿Quieres salir de la captura?</string>
        <string name="id_good_quality">Todo de buena calidad</string>
        <string name="id_hand_closer">Por favor acerca la mano</string>
        <string name="id_hand_further_away">Mueva la mano más lejos</string>
        <string name="id_hand_further_away_ff">Mueva la mano más lejos 4F</string>
        <string name="id_hold_0">Por favor sostenga</string>
        <string name="id_hold_1">Por favor sostenga 1</string>
        <string name="id_hold_2">Por favor sostenga 2</string>
        <string name="id_hold_3">Por favor sostenga 3</string>
        <string name="id_hold_4">Por favor sostenga 4</string>
        <string name="id_hold_5">Por favor sostenga 5</string>
        <string name="id_hold_6">Por favor sostenga 6</string>
        <string name="id_hold_still">Asegúrate de mantenerte quieto hasta la captura automática. </string>
        <string name="id_identy_template_format">Formato de plantilla IDENTY</string>
        <string name="id_image_cd_todo">QUE HACER</string>
        <string name="id_in_front_camera">2.Coloque los dedos frente a la cámara</string>
        <string name="id_index">INDICE    </string>
        <string name="id_index_finger">dedo índice</string>
        <string name="id_inside_guide">Por favor, esté dentro de la guía.</string>
        <string name="id_keep_fingers">1.Extiende y mantén los dedos juntos</string>
        <string name="id_keep_fingers_together">mantener los dedos juntos</string>
        <string name="id_left_thumb"> PULGAR IZQUIERDO</string>
        <string name="id_little">PEQUEÑO   </string>
        <string name="id_little_finger">dedo índice</string>
        <string name="id_location_error_off">Algo es extraño APAGADO</string>
        <string name="id_middle">MEDIO   </string>
        <string name="id_middle_finger">dedo medio</string>
        <string name="id_next">SIGUIENTE</string>
        <string name="id_next_detection">Pasar a la siguiente mano ?</string>
        <string name="id_next_hand_confirm">Siguiente detección Confirmar</string>
        <string name="id_no">NO</string>
        <string name="id_no_match">SIN COINCIDENCIA</string>
        <string name="id_not_good_quality">no tiene buena calidad.</string>
        <string name="id_ok">OK</string>
        <string name="id_pic_qc_title">FALLO EN LA CALIDAD DE LA IMAGEN</string>
        <string name="id_processing">Procesando …</string>
        <string name="id_qc_retake">Necesitamos retomar la foto</string>
        <string name="id_quality_failed">Falló la calidad de la imagen</string>
        <string name="id_retake_additional_tip">Consejos adicionales</string>
        <string name="id_retake_match">Se alcanzó el número máximo de intentos, inténtelo de nuevo</string>
        <string name="id_retake_q">volver a tomar?</string>
        <string name="id_retake_string">volver a tomar</string>
        <string name="id_retake_tip_1">Tus dedos miran hacia la cámara</string>
        <string name="id_retake_tip_2">Tus dedos están dentro de la caja azul</string>
        <string name="id_retake_tip_3">Utilice iluminación interior normal</string>
        <string name="id_retry">Procesar de nuevo</string>
        <string name="id_right_thumb">PULGAR DERECHO</string>
        <string name="id_ring">ANILLO     </string>
        <string name="id_ring_finger">dedo anular</string>
        <string name="id_select_hand">por favor seleccione al menos una mano</string>
        <string name="id_spoof">PARODIA</string>
        <string name="id_spoof_additional_tip">Consejos adicionales</string>
        <string name="id_spoof_question">¿Estás usando manos reales para autenticarte?</string>
        <string name="id_spoof_tip_2">Utilice iluminación interior normal  </string>
        <string name="id_spoof_tip_3">Intente intentar una ubicación / fondo diferente</string>
        <string name="id_spoof_title">Spoof detectado</string>
        <string name="id_stable">Por favor sea estable</string>
        <string name="id_stay_still_blue">3.Quédate quieto dentro del rectángulo azul</string>
        <string name="id_success">Éxito</string>
        <string name="id_success_match"> MATCH EXITOSO</string>
        <string name="id_thumb">PULGAR    </string>
        <string name="id_thumb_finger">dedo índice</string>
        <string name="id_try_again">Intentar otra vez</string>
        <string name="id_try_again_in">Inténtelo de nuevo en : </string>
        <string name="id_wait_auto">4.Espere la captura automática (hasta que se apague el flash)</string>
        <string name="id_wsq_compression">Relación de compresión WSQ</string>
        <string name="id_yes">SI</string>
        <string name="id_zero">0</string>
```

#### 2.5. Uso de la librería

* Una vez instalado el plugin, la aplicación destino heredará el Javascript expuesto por este, el cual expone las siguientes operaciones:
  > * startPhotoCapture
  > * startFindFile
  > * startBarCode
  > * startFrontDocument
  > * startCreditCard
  > * startFingerprint

##### ***startPhotoCapture***

```javascript
    //Captura foto
     onCapturePhoto = () => {
        NativeModules.RNBytteBioLibId.startPhotoCapture(0,0,(response)=>{
            var obj = JSON.parse(response);
            if(obj.CodigoOperacion == "0000" && obj.StatusOperacion == "true"){
                alert(obj.MensajeOriginal+ '\n' + "FileBase64 : " + obj.FileBase64.substr(0,50) + "...");
            } else {
                alert(obj.MensajeOriginal);
            } 
        }); 
    }
```

##### ***startFindFile***

```javascript
  //Busqueda de archivo
    fileSearch = () =>{
            NativeModules.RNBytteBioLibId.startFindFile(idTipo,(response)=>{
                var obj = JSON.parse(response);
                if(obj.CodigoOperacion == "0000" && obj.StatusOperacion == "true"){
                    alert(obj.MensajeOriginal + '\n' + "FileBase64 : " + obj.FileBase64.substr(0,50) + "...");
                } else {
                    alert(obj.MensajeOriginal);
                } 
            }); 
    }
```

##### ***startBarCode***

```javascript
    //Captura documento reverso
    onCaptureBackDocument = () =>{
        NativeModules.RNBytteBioLibId.startBarCode(license,key,timeOut,pais,(response)=>{
            var obj = JSON.parse(response);
            if(obj.StatusOperacion){
                alert(obj.MensajeOriginal + '\n' + '\n' + obj.NombresCompletos + '\n' + "Sexo: " + obj.Sexo + '\n' + "Fecha Nacimiento: " + obj.FechaNacimiento + '\n' + "RH: " + obj.RH);
            } else {
                alert(obj.MensajeOriginal);
            } 
        }); 
    }
```

##### ***startFrontDocument***

```javascript
    //Captura documento frente
    onCaptureFrontDocument = () =>{
        NativeModules.RNBytteBioLibId.startFrontDocument(license,key,timeOut,pais,(response)=>{
            var obj = JSON.parse(response);
            if(obj.StatusOperacion){
                alert(obj.MensajeOriginal + '\n' + '\n' + obj.Nombres + '\n' + obj.Apellidos + '\n' + obj.NumeroCedula);
            } else {
                alert(obj.MensajeOriginal);
            } 
        });
    }
```

##### ***startCreditCard***

```javascript
    //captura tarjeta de credito
    onCaptureCreditCard = () =>{
        NativeModules.RNBytteBioLibId.startCreditCard(license,key,timeOut,(response)=>{
            var obj = JSON.parse(response);
            if(obj.CodigoOperacion == "0000" && obj.StatusOperacion){
                alert(obj.MensajeRetorno + '\n' + "Nombre : " + obj.NombreTarjeta + '\n' + "Numero : " + obj.NumeroTarjeta);
            } else {
                alert(obj.MensajeRetorno);
            } 
        }); 
    }
```

##### ***startFingerprint***

```javascript
    //Captura Biometria dactilar
    onCaptureBiometricDactilar = () =>{
            NativeModules.RNBytteBioLibId.startFingerprint(key,timeOut,finger,namePath,url,netkey,(response)=>{
                var obj = JSON.parse(response);
                if(obj.CodigoOperacion == "0000" && obj.StatusOperacion == "true"){
                    alert(obj.MensajeOriginal);
                } else {
                    alert(obj.MensajeOriginal);
                } 
            }); 
    }
```

```
<string name="OK">0000</string><string name="TimeOut">0001</string>
<string name="Cancelado_a_proposito">0002</string>
<string name="Error_de_Licencia_MicroBlink">0111</string>
<string name="Error_No_tiene_permisos_camara">0112</string>
<string name="Error_de_Licencia_Biometria">0113</string>
<string name="Error_Captura_de_huellas">0114</string>


<string name="timeOut">TimeOut</string>
<string name="Canceladoproposito">Cancelado a proposito</string>
<string name="ErrorLicencia_MicroBlink">Error de Licencia MicroBlink"</string>
<string name="ErrorLicencia_Biometria">Error de Licencia biometria"</string>
<string name="Error_Capturahuellas">Error en la captura de las huellas"</string>
<string name="ErrorLicenciaBiometria">Error licencia de  biometria"</string>

------------------------------
Control de cambios
------------------------------
------------------------------
| 9-nov-2021 | Actualizacion librerías microblink para captura de documentos, cambio de librería para la captura biometria|
```

## Ejemplo Demo

URL:  [http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/bytteTest.zip](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/bytteTest.zip)




