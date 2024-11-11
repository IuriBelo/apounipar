Weather Forecast App (Aplicativo de Previsão do Tempo)
Este é um aplicativo Android desenvolvido com Java para fornecer previsões do tempo de uma cidade especificada. O app utiliza a API de clima do HG Brasil para obter dados meteorológicos e exibi-los em uma interface amigável com RecyclerView, CardView, ViewPager2 e MapFragment. O aplicativo também inclui uma funcionalidade de troca de cidade por QR code usando a biblioteca ZXing.

Funcionalidades
Tela de Splash: Exibe uma tela inicial com logo ou imagem por 3 segundos.
Tela Principal: Exibe um menu de navegação na AppBar e a previsão do tempo com a funcionalidade de troca de cidade.
TabBar com 2 Abas:
Abas de Previsão: Exibe os dados meteorológicos em uma lista, utilizando RecyclerView e CardView.
Abas de Mapa: Exibe um mapa com um marcador fixo para a cidade consultada.
QR Code: Permite ao usuário trocar a cidade através da leitura de um QR code gerado por um outro dispositivo.
Tela Sobre: Exibe informações pessoais como nome, RA, curso e foto do usuário.
Tecnologias Utilizadas
Linguagem: Java
Ambiente: Android Studio
Bibliotecas:
Retrofit (para consumo da API)
Gson (para conversão de JSON)
ZXing (para leitura de QR codes)
ViewPager2 (para abas)
RecyclerView e CardView (para exibir os dados em lista)
Google Maps API (para exibir o mapa)
Configuração do Ambiente
Android Studio: Certifique-se de ter o Android Studio instalado na versão mais recente.
API Key do HG Brasil:
Acesse o site HG Brasil API para gerar uma chave de API.
Substitua "YOUR_API_KEY" no código pela chave gerada.
Passos para Execução
Clonando o Repositório

Para clonar o repositório, execute o comando abaixo:

bash
Copiar código
git clone https://github.com/seu-usuario/weather-forecast-app.git
cd weather-forecast-app
Importando o Projeto no Android Studio

Abra o Android Studio e escolha Open an existing project.
Selecione a pasta do repositório clonado.
Configuração das Dependências

O arquivo build.gradle (Module: app) já contém as dependências necessárias para o projeto. No entanto, você pode garantir que as dependências estejam sincronizadas com o seguinte comando:

gradle
Copiar código
implementation 'com.squareup.retrofit2:retrofit:2.9.0'
implementation 'com.squareup.retrofit2:converter-gson:2.9.0'
implementation 'com.google.code.gson:gson:2.8.8'
implementation 'com.google.zxing:core:3.3.0'
Clique em Sync Now no Android Studio para sincronizar as dependências.

Inserindo a API Key

Não se esqueça de substituir a chave da API na classe MainActivity:

java
Copiar código
Call<WeatherResponse> call = apiService.getWeather("YOUR_API_KEY", cityName);
Executando o Aplicativo

Conecte um dispositivo Android ou use um emulador para testar o aplicativo.
Execute o aplicativo no Android Studio clicando no botão Run.
Estrutura do Projeto
bash
Copiar código
/app
    /src
        /main
            /java
                /com
                    /example
                        /weatherforecastapp
                            MainActivity.java
                            AboutActivity.java
                            RetrofitClient.java
                            WeatherApiService.java
                            WeatherResponse.java
                            QRCodeScannerActivity.java
                        /model
                            WeatherResponse.java
            /res
                /layout
                    activity_main.xml
                    activity_about.xml
                    activity_splash.xml
                /drawable
                    logo.png
                /values
                    strings.xml
                    colors.xml
                    styles.xml
MainActivity.java: Contém a lógica principal de exibição do clima e das abas.
AboutActivity.java: Exibe informações pessoais do usuário.
WeatherApiService.java: Define os endpoints da API de previsão do tempo.
RetrofitClient.java: Configura o Retrofit para consumir a API.
WeatherResponse.java: Modelo para a resposta JSON da API.
QRCodeScannerActivity.java: Gerencia a leitura de QR codes.
Capturas de Tela
Tela Principal

Tela de Previsão

Mapa com Localização








