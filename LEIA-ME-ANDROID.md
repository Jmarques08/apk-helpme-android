# HelpMe! no Android (APK)

Estes arquivos acrescentam o Android ao repositório **Helpme-2**. Depois de enviados, o
GitHub passa a gerar também o **HelpMe-demo.apk**, o mesmo demo do iPhone, que instala
em qualquer celular Android sem loja, sem cabo e sem prazo para expirar.

## O que tem neste pacote

| Arquivo | O que faz |
| --- | --- |
| `.github/workflows/build-apk.yml` | Novo processo do GitHub que monta o APK |
| `android-debug.keystore` | Chave de teste que assina o APK, sempre a mesma |
| `capacitor.config.json` | Atualizado: o app não fica embaixo das barras do Android |
| `package.json` e `package-lock.json` | Atualizados: incluem o Android e o botão voltar |
| `www/index.html` | Atualizado: o voltar do Android volta uma tela, em vez de fechar o app |
| `LEIA-ME-ANDROID.md` | Este guia |

## 1. Enviar para o Helpme-2 (5 min)

1. Descompacte o `helpme-android.zip` (botão direito → **Extrair Tudo…** → **Extrair**).
2. No GitHub, abra o repositório **Helpme-2** → **Add file** → **Upload files**.
3. Na pasta extraída, aperte **Ctrl + A** e arraste tudo para a área pontilhada.
4. Clique em **Commit changes**. O GitHub troca os arquivos antigos pelos novos sozinho.
5. Confira: dentro de `.github/workflows` agora há **dois** arquivos, `build-ipa.yml` e `build-apk.yml`.

## 2. Gerar o APK (5 a 10 min)

1. Abra a aba **Actions**. O processo **Gerar APK do HelpMe! (Android)** começa sozinho.
   O processo do iPhone também roda de novo: é normal.
2. Quando o ícone ficar verde, clique na linha, desça até **Artifacts** e baixe **HelpMe-demo-apk**.
3. Extraia o zip baixado. Dentro está o **HelpMe-demo.apk**.

Se ficar vermelho, clique na etapa com X, copie as linhas acima do erro e mande na conversa com o Claude.

## 3. Instalar no celular Android

1. Mande o **HelpMe-demo.apk** para o celular: WhatsApp (como **Documento**), Google Drive, e-mail ou cabo USB.
2. No celular, toque no arquivo. Se aparecer "instalação bloqueada", toque em **Configurações** e
   ative **Permitir desta fonte** para o app que abriu o arquivo (WhatsApp, Arquivos, Chrome...).
3. Volte e toque em **Instalar**. O app aparece como **HelpMe!**, com o logo.

### Se o Android avisar que o desenvolvedor não é verificado

Desde 30/09/2026, celulares Android no Brasil pedem passos extras para instalar apps de
desenvolvedores não registrados. Você tem duas saídas:

- **Seguir os passos da própria tela**, que podem incluir esperar 24 horas antes de instalar.
- **Registrar o app na conta gratuita de distribuição limitada** do Android (até 20 aparelhos,
  sem taxa). O cadastro pede estes dois dados:
  - Nome do pacote: `app.helpme.demo`
  - Impressão digital SHA-256 da chave:
    `4E:EE:29:92:0E:51:23:C2:94:B4:F4:39:16:55:B3:4E:BF:8A:DB:A5:E9:01:B2:14:EB:54:FB:50:14:13:6C:DF`

## Bom saber

- **Atualizações**: cada APK novo instala por cima do anterior, sem desinstalar, porque a chave é sempre a mesma.
- **Botão voltar**: fecha a janela aberta, volta uma tela e, na tela inicial, só minimiza o app.
- **A chave deste pacote é só para teste.** Para o Google Play, cria-se outra chave, secreta
  (Etapa C do manual "HelpMe! nas lojas"). Se puder, deixe o repositório como **privado**.
