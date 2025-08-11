
# Revesti+ — PWA + Capacitor (Pronto para Play Store e App Store)

Este pacote já vem com:
- `manifest.webmanifest` (PWA)
- `service-worker.js` (offline/cache)
- `assets/icons/*` (ícones)
- `assets/config.js` (marca e texturas)
- `index.html` (app)
- **Template** `capacitor.config.json`

## Como testar como PWA (sem custo)
1. Abra `index.html` em um servidor local (ou publique no GitHub Pages).
2. No celular Android/Chrome, abra o site e use **Adicionar à Tela Inicial**.
3. Ele vai instalar como app e abrir em tela cheia.

## Como empacotar com Capacitor
> Requer Node.js instalado.

```bash
mkdir revesti-cap && cd revesti-cap
npm init -y
npm install @capacitor/core @capacitor/cli --save
npx cap init "Revesti+" "com.revesti.app" --web-dir=./web
mkdir web
# Copie TODOS os arquivos desta pasta para ./web
cp -r /CAMINHO/DESTA/PASTA/* ./web
# Depois:
npx cap add android
npx cap add ios   # precisa de Mac
npx cap sync
npx cap open android   # abre no Android Studio
npx cap open ios       # abre no Xcode (no Mac)
```

No Android Studio/Xcode você gera os arquivos da loja (AAB/IPA).

## Dicas para aprovação
- Preencha título, descrição, screenshots.
- Política de privacidade (pode hospedar uma página simples no GitHub Pages).
- Explique que o app processa imagens **localmente** (sem backend).

## Próximos passos
- Substituir ícones por artes finais (em `assets/icons`).
- Trocar cores e nome em `assets/config.js` e `manifest.webmanifest`.
- (Opcional) Integrar Firebase para login/galeria/ranking.
