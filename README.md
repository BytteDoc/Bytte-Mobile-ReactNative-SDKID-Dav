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

#### 2.2.1.2 MICROSOFT

Una vez instalado NPM (sistema de gestión de paquetes). Se debe ejecutar el siguiente comando en la terminal.

``` vsts-npm-auth -config .npmrc```

este comando creara un archivo .npmrc en la ruta por defecto C:\Users\USER\\.npmrc

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






