# Metrônomo de cadência: gerar o APK

Este projeto empacota a página do metrônomo como app Android (Capacitor).
O APK gerado é de teste (debug) e serve para uso pessoal.

## Opção A: sem instalar nada (GitHub)
1. Crie uma conta gratuita em github.com e um repositório novo.
2. Envie todo o conteúdo desta pasta para o repositório (inclusive a pasta .github).
3. No repositório, abra a aba Actions, escolha "Gerar APK" e clique em Run workflow.
4. Quando terminar (alguns minutos), abra a execução e baixe o arquivo
   "metronomo-cadencia-apk" na seção Artifacts. Dentro do zip está o app-debug.apk.
5. Passe o APK para o celular e instale. O Android vai pedir para permitir
   a instalação de apps de fontes desconhecidas.

## Opção B: no seu computador
Precisa de Node.js 18+, Java 17 e Android Studio (ou só o Android SDK).
    npm install
    npx cap add android
    npx cap sync android
    cd android && ./gradlew assembleDebug
O APK fica em android/app/build/outputs/apk/debug/app-debug.apk

## Para mudar o app
Edite www/index.html, rode "npx cap sync android" e gere o APK de novo.

## Observação
Com a tela bloqueada o Android pode pausar o som. O app pede para manter a
tela ligada durante o treino. Para tocar com a tela apagada seria preciso um
serviço em segundo plano nativo (posso ajudar com isso numa próxima versão).
