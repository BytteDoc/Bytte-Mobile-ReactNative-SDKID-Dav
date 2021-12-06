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

#### 2.2.1 Configuración archivo .npmrc

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

#### 2.2.2 Instalación 

`$ npm install react-native-bytte-bio-lib-id`


Una vez instalado el plugin, se debe realizar la consulta a la aplicación para verificar que este quedó correctamente instalado.

#### 2.3. Configuración nativo iOS (XCode)

######   Adicionar la implementación bytte a su proyecto NPM
para esta implementación se puede generar desde npm integrando de la siguiente forma: 

``` npm install react-native-bytte-bio-lib-id```

Luego de instalar las dependencias npm se ingresa a la carpeta ***ios*** y se ejecuta el comando `pod install`

    $ cd ios
    $ pod install

![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/podinstall.png)

Luego se ingresa al proyecto IOS y en la sección  ***Development Pods*** se busca la carpeta  ***RNBytteBioLibMiiD*** donde se encuentra los archivos correspondientes a la libreria. En la carpeta ***Frameworks*** se encuentran los binarios que deben ser embebidos de manera local al proyecto.

![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/framework4.png)

Una vez agregados se valida que se encuentren  ***Embed & sign*** 

![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/framework5.png)

######   Configuración Framework Search Paths

Se optiene la ruta donde se encuentran los Framework bytte y se configura en Framework Search Paths

Ruta por defecto : ***Ruta_Proyecto***/bytteTest/node_modules/react-native-bytte-bio-lib-miid/ios/Frameworks

![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/framework2.png)

######   Configuración Pod RNBytteBioLib Framework Search Paths

Se optiene la ruta donde se encuentran los Framework bytte y se configura en ***pod*** ***RNBytteBioLibMiiD*** Framework Search Paths

Ruta por defecto : ***Ruta_Proyecto***/bytteTest/node_modules/react-native-bytte-bio-lib-miid/ios/Frameworks

![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/framework3.png)

###### Licencia captura dactilar

Bytte proporciona el archivo de licencia para captura dactilar. Este archivo debe ser guardado en la raiz del proyecto IOS y embebido como recurso en la aplicación nativa tal como lo muestra la siguiente imagen.

![Directories](http://www.bytte.com.co/ftpaccess/Varios/CarlosG/ReactNative/framework6.png)

El nombre del archivo se envía por parámetro ***(namePath)*** en la captura dactilar.


######   Permisos
Los permisos en runtime deben ser solicitados por la app para el uso de bytte es necesario el siguiente:
configurar en el archivo Info.plist para el uso de la ***Camara***

`Privacy - Camera Usage Description`

# 2.4. Configuración  Android

## Captura de Insumos 
El app debe solicitar los permisos  en tiempo de ejecución antes de usar la funcionalidad y validar que el permiso fue otorgado

### Verificamos la configuracion cordova para android y adicionamos el plugin que se les entrega.
### tomar el path del plugin descargado
``` terminal 
cordova platform add android
cordova plugin add ../com.bytte.cordova.cuentadigital.plugin.face/CDVBytteBioLibV3/

```

#### Para la configuración de Android ahora se maneja por maven para el uso de estas dependencias debemos tener en cuenta lo siguiente: confirmar los datos de username y token. Para solicitarlos a bytte antes de su desarrollo. Estos nos dan el acceso a las dependencias necesarias de las capturás de huellas, documento colombiano de hologramas


### soporte a arquitecturas arm 32 y 64 bits 
``` gradle


android{ 
    defaultconfig  despues de 
    versionName ingresamos 
    ndk {abiFilters  “armeabi-v7a”, "arm64-v8a"}


  maven {
         url 'https://multifactorbyttelibrary.pkgs.visualstudio.com/BytteSDKLibraryX/_packaging/SDKBytteV2/maven/v1'
         name 'SDKBytteV2'
        credentials {
            username ""
            password ""
        }
    }
```

## licencias Documentos 
> * Identificador de la aplicacion 'packagename' ejm: *com.biometric.bytte.casbauth
> * Se esntrega una cadena con el siguiente formato:
> * sRwAAAAYY29tLmxvc2FuZGVzcHJlcGFnby50YXBw65mSy/13Bcc1rGbVKla2wsuEGRZ8bunSfSt8+JnzW+QzG2aIrzOH+kk1UixKehUiOG62x8FNjIF1CcbKM4aLgHHdOLni7+UMfDpYe+pky26XC/YxvnD5cYCQ2dI4RhqJHKSZiLH6fwLfZXVPnF3wgGyZMRrmOW/yu0V0wLaOEpC8rJaDxIwQvwTOm0/BL5/Y901Z+dALX1U/6KmeP+deJy1oshQ85A4IgH4uNmSStQAnor4=
Esta licencia es necesaria para el uso del sdk y captura de documentos.


# licencias Biometria

### Parametros
**Para el uso de la licencia Biometria es necesario registrar el app Pakage ID en la paltaforma de google developer**  
* **Para generar la llave safetyNet api key busca los detalles del resgistro**
en https://developer.android.com/training/safetynet/attestation 
* **Desarrollador SHA1 Key. Cada desarrollador necesita un par de claves para firmar aplicaciones: una para debug y otra para el modo de release. Estos HASH también deben estar asociados con la licencia.**
* esta licencia es unica por equipo ej: un desarrollador que tiene acceso a variantes de compilacion debe generar unas para debug y otra para release por cada projecto.



**Se entrega un archivo y este se ingresara en el directorio: android/app/src/assets**
<p align="center" >
  <img src="src/assets.png"  width="400" height="400">
</p>

## licencia  Android para el uso de huellas
* **crear una carpeta en el direccorio android llamada assets**
Dentro de esa carpeta depositamos el archivo de licencia que se generara para la implementación en debug y otra para reléase


## Luego vamos a generar la llave safetynet 
https://developer.android.com/training/safetynet/attestation
en la url se muestran los detalles para solicitar la llave safetynet 




```    
## configuracion colores de la pantalla de huellas
>boxes -> color de borde  del cuadro de la camara
>boxes_transparent -> color del recuadro  entre el header y el footer
>colorPrimary -> color del footer y el header 

    ```  xml
    <color name="boxes">#FF5722</color>
    <color name="boxes_transparent">#FF5722</color>
    <color name="colorPrimary">#FFC107</color>
    <color name="colorPrimaryDark">#FF5722</color>

    ```
## configuracion en español para mensajes  huellas
vamos a la carpeta res/values/strings.xml

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
        <string name="id_exit_text">¿Quieres salir de Capture?</string>
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
        <string name="id_index">ÍNDICE    </string>
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


## configuracion colores de la pantalla de facial
### Colores para personalizar la vista 
Estos colores se toman de la configuracon de la app 
>id_box -> color del mensaje 
>id_face_boxes -> color del del borde
>colorPrimary -> color del footer y el header 
```
  
    <color name="id_box">#FF5722</color>
    <color name="id_face_boxes">#8BC34A</color>
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
| 9-nov-2021 | Actualizacion librerias microblink para captura de documentos, cambio de librerias para la captura biometria|




