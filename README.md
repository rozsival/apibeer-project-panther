# 🐆 Projekt Panther – Lokální AI cluster

Tento repozitář obsahuje technickou prezentaci vytvořenou pro vývojářský meetup. Zaměřuje se na příběh, volbu hardwaru a úskalí při stavbě vlastního open-source AI clusteru. 

Prezentace je vizuálně formátovaná do cyberpunk/neonového stylu obohaceného originálními 3D rendery a běží na populárním webovém prezentačním frameworku [Slidev](https://sli.dev/).

> **Co je Projekt Panther?**
> Cesta od prvotní vize a nákupu hardwaru až k softwarové stabilizaci pro bleskové lokální inference LLM modelů. Ukázková sestava je postavená na procesoru AMD Ryzen 9, 192 GB RAM a dvou grafických kartách Radeon R9700 AI Pro (s celkem 64GB VRAM), vyladěná pro extrémní propustnost (až 861 tok/s v prefill fázi) bez asistence cloudu.

## 🚀 Přehrání prezentace lokálně

Pro spuštění a prohlížení slidů na vlastním počítači je potřeba Node.js a balíčkovací systém (v tomto projektu `pnpm`).

```bash
# 1. Instalace všech závislostí knihovny Slidev
pnpm install

# 2. Spuštění lokálního webového serveru a renderovacího enginu
pnpm run dev
```

Po úspěšném sestavení bude prezentace dostupná k prohlížení i interaktivní úpravě na adrese http://localhost:3030/. Do PDF formátu lze slajdy exportovat komandem `pnpm run build` (nebo pomocí interních Slidev exportních utilit).

## 🗄️ Infrastrukturní repozitář stroje

Prezentace popisuje hardware a softwarový stack, jehož kompletní verzovaná konfigurační struktura včetně instalačních skriptů, proxy utilit a orchestrace vLLM/Llama.cpp se nachází ve spřáteleném repozitáři:

👉 **[github.com/rozsival/panther-minor](https://github.com/rozsival/panther-minor)**

---
### 👨‍💻 Autor a kontakt
* **Vít Rozsíval** 
* GitHub: [@rozsival](https://github.com/rozsival), LinkedIn: [@vitrozsival](https://www.linkedin.com/in/vitrozsival/)
