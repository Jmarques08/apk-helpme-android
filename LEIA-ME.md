# HelpMe! — demo navegável no iPhone (.ipa)

Este projeto transforma o demo **HelpMe! App** (Cliente, Profissional e Admin, com
cenários prontos e o guia da demonstração) num app de iPhone.

- O app inteiro vai **dentro do iPhone**: funciona **sem internet** e não depende de site nenhum.
- Nome na tela de início: **HelpMe!**, com o logo do demo.
- Tem ID próprio (`app.helpme.demo`), então pode ficar instalado **junto** com o app "Help Me"
  do APK sem um substituir o outro.
- Como no demo online, os pedidos criados ficam só na memória: ao fechar o app de vez
  (deslizar para cima no seletor de apps), a demonstração recomeça do zero.

O .ipa é gerado pelo **GitHub**, num Mac na nuvem, de graça. Você não precisa ter Mac.

Este pacote também gera o app **Android** (HelpMe-demo.apk): veja o arquivo `LEIA-ME-ANDROID.md`.

---

## Parte 1 — Gerar o .ipa no GitHub (≈ 10 min)

1. Entre em **github.com** (crie a conta, se ainda não tiver).
2. Clique em **New repository** → nome `helpme-demo-ios` → **Create repository**.
   - **Public**: Mac na nuvem grátis e sem limite (o código fica visível para qualquer pessoa).
   - **Private**: também funciona, dentro da cota gratuita mensal do GitHub.
3. Na página do repositório, clique em **uploading an existing file**.
4. Descompacte o `helpme-demo-ios.zip` e **arraste todo o conteúdo da pasta**
   (não a pasta em si) para a página. Clique em **Commit changes**.
5. Confira se a pasta `.github/workflows` subiu (pastas que começam com ponto às vezes
   ficam ocultas). Se não aparecer: **Add file → Create new file**, digite o nome
   `.github/workflows/build-ipa.yml`, cole o conteúdo desse arquivo e salve.
6. Abra a aba **Actions**. O processo "Gerar .ipa do HelpMe! (iPhone)" começa sozinho
   (ou clique nele → **Run workflow**). Leva uns 5–10 minutos.
7. Quando ficar verde ✅, clique no processo e, embaixo, em **Artifacts**, baixe
   **HelpMe-demo-ipa**. Dentro do zip está o **HelpMe-demo.ipa**.

## Parte 2 — Instalar no iPhone (com Apple ID grátis)

O .ipa sai **sem assinatura**, e o iPhone só instala apps assinados. O programa
**Sideloadly** (sideloadly.io, para Windows ou Mac) assina com o seu Apple ID e instala:

1. Instale o **Sideloadly** no computador. No Windows, instale também o **iTunes** e o
   **iCloud** baixados do site da Apple (não da Microsoft Store).
2. Ligue o iPhone no cabo USB e toque em **Confiar** no iPhone.
3. Abra o Sideloadly, arraste o **HelpMe-demo.ipa**, digite seu **Apple ID** e clique em **Start**.
   (Dica: se tiver, use um Apple ID secundário.)
4. No iPhone, ative o **Modo de Desenvolvedor**:
   Ajustes → Privacidade e Segurança → Modo de Desenvolvedor → ligar → reiniciar.
5. Autorize o app: Ajustes → Geral → **VPN e Gerenciamento de Dispositivos** →
   toque no seu Apple ID → **Confiar**.
6. Pronto: o ícone **HelpMe!** aparece na tela de início.

### Limites da conta grátis
- O app **para de abrir depois de 7 dias**. Para renovar, repita o passo 3 (o Sideloadly
  também renova sozinho se o iPhone e o computador estiverem na mesma rede Wi-Fi).
- No máximo **3 apps** instalados assim ao mesmo tempo (este e o "Help Me" contam 2).
- Só dá para instalar em aparelhos ligados ao seu computador.

## Para mostrar a outras pessoas (TestFlight / App Store)

Precisa da conta **Apple Developer** (US$ 99/ano). Com ela, o app é assinado de verdade e
pode ir para o **TestFlight** (link de teste para até 10.000 pessoas) ou para a App Store.
Nesse caso, registre o Bundle ID `app.helpme.demo` na conta e adicione o certificado e o
perfil de distribuição ao processo do GitHub.

---

## O que mudou em relação ao demo online

- As fontes (Manrope e Source Serif 4) estão dentro do app, em `www/fonts`.
- Espaço certo para a barra de status, o notch e o Dynamic Island, e para a barra de
  gestos na parte de baixo.
- Sem zoom automático ao tocar em campos de texto e sem o "efeito elástico" ao rolar.
- Corrigida uma caixa branca vazia que aparecia no pedido de **Elétrica**.

## Para mudar algo

- **O app em si**: `www/index.html` (é o demo inteiro, HTML + CSS + JavaScript).
- **Nome que aparece no iPhone**: `ios/App/App/Info.plist` → `CFBundleDisplayName`.
- **Ícone e tela de abertura**: troque `assets/icon.png` (1024×1024), `assets/splash.png`
  e `assets/splash-dark.png` (2732×2732) e rode `npm run assets`.

Cada alteração enviada ao GitHub gera um .ipa novo automaticamente.
