![React-Native](https://revelry.co/wp-content/uploads/2019/05/react-native-UX-design.gif)

react-native-aula é um projeto para demonstração da tecnologia React Native com integração com o Firebase.

# Começando

## Pré-requisitos

É necessário que se tenha instalado o NodeJs a partir da 8.3 e o gerenciador de pacotes Yarn.

Node: https://nodejs.org/en/

Yarn: https://yarnpkg.com/en/

## Guia de Instalação

 - Siga os passos deste tutorial:

    https://docs.rocketseat.dev/ambiente-react-native/introducao

- Você também pode consultar a documentação oficial do React Native aqui:

    https://facebook.github.io/react-native/docs/getting-started
 

Após a instalação e a configuração do seu ambiente de simulação. 

 - Crie uma pasta e abra ela no terminal
 - rode o comando ```react-native init 'nomeDoProjeto'```


 ## Configuração Firebase

 ### Criação do Projeto

  - Crie uma conta no Firebase: 
  https://console.firebase.google.com
  - Crie um Projeto

No Overview do projeto, registre um app android, serão pedidos os campos:
 - Nome do pacote do Android (Você encontra no arquivo AndroidManifest.xml na pasta ```android/main/``` do seu projeto).
 - Nome do App
 - Certificado de assinatura de depuração SHA-1 (Você encontra como conseguir neste link: https://developers.google.com/android/guides/client-auth).

### Configuração da SDK

 - Faça o download do arquivo ```google-services.json``` e coloque na pasta android/app).
 - Instale o pacote ```react-native-firebase``` com o comando ```yarn add react-native-firebase```.
 - Faça o link do pacote com o código nativo do app com o comando ```react-native link react-native-firebase```

 - Entre na pasta ```android``` e no arquivo ```build.gradle``` adicione as dependências abaixo:

 ```js
    buildscript {
        repositories {
            google()
        }
        dependecies {
            classpath("com.google.gms:google-services:4.3.2")
        }
    }
    allprojects {
    ...
        repositories {
            google()  
            ...
        }
    }
```
 - Entre na pasta ```android/app``` e abra o arquivo ```build.gradle``` e adicione as dependências abaixo:

 ```js
    
    dependecies {
        implementation "com.google.firebase:firebase-analytics:17.2.0"
    }
   //No final do arquivo adicione:
   apply plugin: "com.google.gms.google-services"
```
Após estes passos seu app estará com a SDK do Firebase configurada.

Para finalizar a instalação da SDK abra duas janelas do terminal, em uma rode o comando ```npm start -- --reset-cache``` e na outra rode o aplicativo com o comando ```react-native run-android```.