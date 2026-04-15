---
theme: default
colorSchema: dark
background: /panther-radeon.png
title: "Projekt Panther – Lokální AI cluster"
info: |
  ## Projekt Panther
  Cesta k vlastnímu lokálnímu AI clusteru na platformě AMD.
class: text-center
transition: slide-left
comark: true
fonts:
  sans: "Inter"
  mono: "Fira Code"
---

<style>
.slidev-layout {
  background: linear-gradient(135deg, #1f1025 0%, #0e0c14 45%, #050505 100%);
}
</style>

<div class="bg-black/70 p-12 rounded-3xl border border-red-500/30 backdrop-blur-md shadow-[0_0_50px_rgba(0,0,0,0.8)] inline-block mt-16 max-w-fit mx-auto">

# Projekt Panther 🐆

<div class="mt-6 mb-6 h-px w-32 bg-gradient-to-r from-transparent via-red-500 to-transparent mx-auto"></div>

## Cesta k vlastnímu lokálnímu AI clusteru

<div class="mt-4 text-xl font-light op-90 text-gray-300">
Od vize přes hardwarové limity až k agentní AI
</div>

</div>

<div class="abs-b m-6 left-0 right-0 text-center animate-pulse text-sm opacity-80">
  <span class="bg-black/50 px-5 py-2.5 rounded-full backdrop-blur-sm border border-red-500/30 shadow-[0_0_15px_rgba(220,38,38,0.3)] text-red-100 font-bold tracking-wider">
    🚀 STARTUJEME <carbon:arrow-right class="inline ml-1" />
  </span>
</div>

<!--
Dobrý den všem. Dnes vám představím projekt Panther. Není to jen o tom, že jsem si postavil drahé PC. Je to o cestě od pouhého konzumenta AI k architektovi vlastní infrastruktury, která mi dává svobodu, o jaké se v cloudu může jen zdát.
-->

---
transition: fade
layout: two-cols
---

# Proč vlastní cluster?

### ☁️ Cloud vs 🏠 Lokál

<br/>

<v-clicks>

- 🛠️ **Hands-on experience** <br/> Pochopení architektury LLM v praxi.
- 💰 **Ekonomika** <br/> Předpoklad zdražování a omezení dostupnosti cloudových API.
- ⚡ **Kritická infrastruktura** <br/> Nedostatek napájení v datacentrech – lokální AI jako nutnost.
- 🧠 **Zvídavost** <br/> Touha poznat, co se děje pod pokličkou.

</v-clicks>

::right::

<div class="h-full flex items-center justify-center p-8">
  <div class="text-[10rem] op-20 transition-all hover:scale-110 hover:op-50 duration-500 cursor-default">
    <carbon:cloud-data-ops />
  </div>
</div>

<!--
Proč do toho jít? Nechci být jen uživatelem, chci tomu rozumět. Věřím, že cloudová AI budou brzy velmi drahá a hůře dostupná kvůli energetickým limitům. Pokud chcete mít AI k dispozici 24/7 bez ohledu na politiku OpenAI nebo Anthropic, musíte mít vlastní železo.
-->

---
transition: slide-up
layout: image-right
image: /panther-exterior.jpg
---

# Plán a sbírání dat 📊

<div class="text-lg mb-8 text-gray-400">Hardware jako investice</div>

- **Zájem:** Open-weights modely (zejména rodina Qwen).
- **Volba GPU:** Proč padla NVIDIA (nedostupnost/cena) a Mac Studio (uzavřenost).

<br/>

### 🛠️ Finální sestava:

<v-clicks>

<div class="grid grid-cols-3 gap-4 mt-2">

<div class="bg-gray-800/50 p-4 rounded-lg border-t-4 border-blue-500">
  <div class="text-sm text-blue-400">CPU</div>
  <div class="font-bold text-sm">Ryzen 9</div>
</div>

<div class="bg-gray-800/50 p-4 rounded-lg border-t-4 border-red-500">
  <div class="text-sm text-red-400">GPU</div>
  <div class="font-bold text-sm">2x Radeon R9700 AI Pro (64GB VRAM)</div>
</div>

<div class="bg-gray-800/50 p-4 rounded-lg border-t-4 border-green-500">
  <div class="text-sm text-green-400">RAM</div>
  <div class="font-bold text-sm">192 GB DDR5</div>
</div>

</div>

</v-clicks>

<!--
Výběr byl pragmatický. NVIDIA je aktuálně cenově mimo pro jednotlivce. Mac Studio je sice skvělé, ale je to "černá skříňka" bez možnosti upgradu. Zvolil jsem cestu vlastního PC s Radeony. Těch 192 GB RAM vypadalo jako overkill, ale pro TMPFS a multitasking je to naprostý game-changer.
-->

---
transition: slide-left
---

# Logistika a stavba 📦

<div class="text-lg text-gray-400 mb-4">The "Baby" Moment</div>

<div grid="~ cols-2 gap-4">

<div class="mt-0">

- 💰 **Hodnota:** 158 000 CZK (včetně daně).
- 🚗 **Transport:** Prahou v koloně – "jízda s dítětem".
- 🏗️ **Stavba po letech:** Manuály, pečlivost a konzultace s AI (Gemini).
- ⚙️ **Komponenty:** Fractal Torrent (airflow) + Dark Rock Pro (ticho).

</div>

<div class="flex justify-center items-start -mt-8 w-full" v-motion :initial="{ scale: 0.9, opacity: 0, y: 50 }" :enter="{ scale: 1, opacity: 1, y: 0, transition: { delay: 300, duration: 800, type: 'spring', stiffness: 250 } }">
  <img src="/panther-interior.jpg" class="rounded-xl shadow-2xl w-full h-[360px] object-cover border-4 border-gray-800" alt="Panther Interior" />
</div>

</div>

<!--
Když vezete hardware za 150 tisíc z Holešovic na Pankrác, jedete v koloně velmi opatrně. Samotná stavba po letech byla výzva – potil jsem se, abych nic nepokazil, a Gemini mi dělala virtuálního asistenta u manuálu k základní desce.
-->

---
transition: fade
layout: default
---

# Porodní bolesti: Lessons Learned 💥

<div class="grid grid-cols-3 gap-6 mt-16">

<div v-click="1" class="bg-gray-800/80 p-6 rounded-xl shadow-lg border border-gray-700 hover:-translate-y-2 transition-transform">
  <div class="text-4xl mb-4 text-red-500"><carbon:linux /></div>
  <h3 class="text-red-400 text-xl font-bold mb-2">Kernel Hell</h3>
  <p class="text-sm text-gray-300">Ubuntu 24.04 LTS neznalo HW (nefunkční síť) -> nutný okamžitý upgrade na 25.10.</p>
</div>

<div v-click="2" class="bg-gray-800/80 p-6 rounded-xl shadow-lg border border-gray-700 hover:-translate-y-2 transition-transform">
  <div class="text-4xl mb-4 text-yellow-500"><carbon:warning /></div>
  <h3 class="text-yellow-400 text-xl font-bold mb-2">vLLM náraz</h3>
  <p class="text-sm text-gray-300">Chybějící podpora pro RDNA 4. Projekt silně optimalizován pro enterprise CUDA.</p>
</div>

<div v-click="3" class="bg-gray-800/80 p-6 rounded-xl shadow-lg border border-gray-700 hover:-translate-y-2 transition-transform">
  <div class="text-4xl mb-4 text-blue-500"><carbon:plug /></div>
  <h3 class="text-blue-400 text-xl font-bold mb-2">Hardwarový fail</h3>
  <p class="text-sm text-gray-300">Špatně zvolený zdroj způsoboval neviditelné podtaktování GPU při zátěži.</p>
</div>

</div>

<!--
Nebyl to hladký start. Ubuntu 24.04 nemělo ovladače pro mou síťovku, musel jsem na 25.10. Pak přišlo zklamání s vLLM, které na mém HW neběželo. A největší lekce? Špatně zvolený zdroj. Musel jsem to celé rozebrat a vyměnit ho, aby grafiky dostaly stabilitu, kterou potřebují.
-->

---
transition: slide-up
---

# Stavíme finální stack: Llama.cpp 🦙

<div grid="~ cols-2 gap-8" class="mt-8">
<div>

<v-clicks>

- 🏗️ **Native Build:** Build přímo v ROCm dev image pro RDNA 4.
- 🐙 **Panther-Minor:** Vlastní správa infrastruktury v Gitu.
- 🚀 **Rychlost:** Qwen3 30B v 8bit kvantizaci sází **70 tok/s**.
- 🗜️ **Kvantizace:** Následný přechod na Unsloth Dynamic Q4_K_XL.
  <br/>
  <a href="https://unsloth.ai/docs" target="_blank" class="inline-flex items-center gap-3 mt-4 ml-7 px-5 py-2.5 bg-gray-800 hover:bg-purple-900/40 text-purple-300 text-base font-semibold rounded-xl border border-gray-700 hover:border-purple-500 transition-all no-underline shadow-lg cursor-pointer hover:scale-105">
    <div class="bg-gray-100 rounded flex items-center justify-center p-1"><img src="https://unsloth.ai/docs/~gitbook/image?url=https%3A%2F%2F2815821428-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Forganizations%252FHpyELzcNe0topgVLGCZY%252Fsites%252Fsite_mXXTe%252Flogo%252F5W6YArempcQo3pu6l9mk%252Funsloth%2520final%2520space%2520black.png%3Falt%3Dmedia%26token%3Da204ba01-b272-4059-a60d-139dc5d1245d&width=260&dpr=3&quality=100&sign=1e67a6bb&sv=2" class="h-6 object-contain" alt="Unsloth" /></div> unsloth.ai/docs
  </a>

</v-clicks>

</div>
<div class="flex flex-col gap-4" v-click="1">

<div class="text-sm text-gray-400 mb-[-10px] ml-2">Nativní build pro ROCm 7</div>

```bash
make HIPCXX="$(hipconfig -l)/clang" \
     HIP_PATH="$(hipconfig -R)" \
     AMDGPU_TARGETS="gfx1201" \
     LLAMA_HIPBLAS=1 \
     -j $(nproc)
```

</div>
</div>

<!--
Ollamu jsem nechal za sebou a přešel na llama.cpp. Postavil jsem si nativní build přímo pro svou architekturu. Veškerou konfiguraci držím v repu Panther-Minor. Objevil jsem svět kvantizací a zjistil, že Unsloth modely jsou aktuálně absolutní špička v poměru přesnost/paměť.
-->

---
transition: fade
layout: statement
---

# Stabilizace: Power & VRAM Management 🔋

<div class="w-full mx-auto max-w-2xl text-left text-lg">

<div class="flex items-center gap-4 my-6">
  <div class="i-carbon-linux-alt text-3xl text-orange-400"></div>
  <span><strong>Kernel Tuning:</strong> Oprava power managementu přes parametry GRUBu.</span>
</div>

<div class="flex items-center gap-4 my-6">
  <div class="i-carbon-network-4 text-3xl text-blue-400"></div>
  <span><strong>VRAM Orchestrace:</strong> Vlastní proxy pro auto-unload nečinných modelů.</span>
</div>

<div class="flex items-center gap-4 my-6">
  <div class="i-carbon-virtual-machine text-3xl text-green-400"></div>
  <span><strong>Ochrana KV Cache:</strong> Přepnutí do Single-Tenant režimu (<code>--parallel 1</code>).</span>
</div>

</div>

<!--
Musel jsem ladit kernel, aby karty v idle nezlobily. Také jsem si napsal vlastní proxy, která inteligentně uvolňuje modely z paměti, aby karty zbytečně nehřály, když se nic neděje. Klíčem k rychlosti prefillu bylo ale vynucení jednoho slotu v llama serveru.
-->

---
layout: center
class: text-center
---

# Benchmarky 🚀

<div class="flex justify-between items-end mb-8 w-full max-w-4xl mx-auto">
  <div class="text-2xl text-purple-400">(The tok/s Flex)</div>
  
  <div class="bg-red-900/30 text-red-500 border border-red-500/50 rounded-xl px-5 py-2 flex items-center gap-3 shadow-[0_0_20px_rgba(220,38,38,0.3)] backdrop-blur-md relative overflow-hidden">
    <div class="relative flex items-center gap-3">
      <div class="w-3 h-3 bg-red-500 rounded-full relative shadow-[0_0_8px_rgba(239,68,68,1)]">
        <div class="absolute inset-0 rounded-full border border-red-500 animate-ping"></div>
      </div>
      <span class="font-bold tracking-wider uppercase text-sm">Live Demo</span>
    </div>
  </div>
</div>

<div class="bg-gray-900/80 rounded-xl p-8 border border-gray-700 shadow-[0_0_50px_rgba(168,85,247,0.1)] inline-block w-full max-w-4xl">

<table class="w-full text-left table-auto border-collapse">
  <thead>
    <tr class="border-b border-gray-700 text-gray-400">
      <th class="p-4">Model</th>
      <th class="p-4">Velikost</th>
      <th class="p-4">Prefill (tok/s)</th>
      <th class="p-4">Output (tok/s)</th>
    </tr>
  </thead>
  <tbody>
    <tr class="border-b border-gray-800/50">
      <td class="p-4">Různé MoE</td>
      <td class="p-4 text-gray-500">do 30B</td>
      <td class="p-4 font-mono text-blue-400">~2500-4500</td>
      <td class="p-4 font-mono">~50-70</td>
    </tr>
    <tr class="bg-purple-900/20 text-xl font-bold">
      <td class="p-4 text-purple-300">Gemma 4 Dense</td>
      <td class="p-4 text-purple-300">31B</td>
      <td class="p-4 font-mono text-purple-400">~600-900 🤯</td>
      <td class="p-4 font-mono text-purple-400">~18-23</td>
    </tr>
  </tbody>
</table>

</div>

<div class="mt-8 text-sm text-gray-400 flex justify-center items-center gap-2">
  <carbon:settings-adjust /> Tuning: Optimalizace <code>n-batch</code> 4096 a <code>n-ubatch</code> 1024.
</div>

<!--
Tady vidíte reálná čísla. Díky optimalizaci batchingu jsem dosáhl fyzického limitu PCIe sběrnice a paměti karet. Prefill přes 900 tokenů za sekundu u 31B dense modelu je na domácí setup naprostý nesmysl, ale je to realita.
-->

---
transition: slide-left
layout: two-cols
---

# Co od toho nečekat? 🤔

<div class="text-lg text-gray-400 mb-8">Očekávání vs. Realita</div>

<v-clicks>

<div class="bg-red-900/20 p-4 rounded-lg border-l-4 border-red-500 mb-4">
  <carbon:close-outline class="inline text-red-500 mr-2" />
  <strong>Není to "bezedný" Claude s 1M kontextem.</strong>
</div>

<div class="bg-green-900/20 p-4 rounded-lg border-l-4 border-green-500 mb-4">
  <carbon:checkmark-outline class="inline text-green-500 mr-2" />
  Nutnost agilního přístupu: <strong>Plan-Confirm-Implement.</strong>
</div>

<div class="bg-green-900/20 p-4 rounded-lg border-l-4 border-green-500">
  <carbon:checkmark-outline class="inline text-green-500 mr-2" />
  Dělení tasků do menších celků a agresivní čištění kontextu.
</div>

</v-clicks>

::right::

<div class="h-full flex items-center justify-center p-8">
  <div class="text-center w-full bg-gray-800/30 border border-gray-700 rounded-xl p-8 shadow-2xl relative overflow-hidden">
    <div class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-red-500 to-orange-500"></div>
    <carbon:warning-alt class="text-6xl mx-auto mb-4 text-orange-400 op-80" />
    <h3 class="text-2xl font-bold text-gray-200">Kontext je <br/> vzácný zdroj</h3>
  </div>
</div>

<!--
Buďme upřímní – nemůžete do toho sypat historii jako do Clouda. Chce to změnit workflow. Musíte pracovat agilně, po menších kouscích. Ale víte co? Tahle disciplína paradoxně vede k mnohem přesnějším výsledkům i u největších modelů v cloudu.
-->

---
layout: default
---

# Přidaná hodnota: Multitasking ⚡

<div class="text-lg text-gray-400 mb-8">Když se RAM a rychlé I/O setkají v praxi.</div>

<div grid="~ cols-2 gap-8">

<div>
<v-clicks>

- <div class="mb-4">🚀 <strong>TMPFS:</strong> <br/><span class="text-sm text-gray-400">Využití 192 GB RAM pro bleskové I/O operace.</span></div>
- <div class="mb-4">🔁 <strong>Multitasking:</strong> <br/><span class="text-sm text-gray-400">Paralelní inference + build velkého Rust monorepa (6-8 min).</span></div>
- <div class="mb-4">🔒 <strong>Soukromí:</strong> <br/><span class="text-sm text-gray-400">AI i běhové prostředí agentů (OpenCode/OpenFang) na jednom místě bez úniku dat.</span></div>

</v-clicks>
</div>

<div v-click="2" class="relative">
  <div class="absolute -inset-1 bg-gradient-to-r from-green-500 to-blue-500 rounded-lg blur opacity-25"></div>
  <div class="relative bg-gray-900 p-6 rounded-lg font-mono text-sm border border-gray-700 shadow-2xl">
    <div class="flex gap-2 mb-4 border-b border-gray-800 pb-2">
      <div class="w-3 h-3 rounded-full bg-red-500"></div>
      <div class="w-3 h-3 rounded-full bg-yellow-500"></div>
      <div class="w-3 h-3 rounded-full bg-green-500"></div>
    </div>
    <div class="text-green-400">$ cargo build --release</div>
    <div class="text-gray-400 mt-2">Compiling 850 crates...</div>
    <div class="text-yellow-400 mt-1">[████████░░░░░░░░░░] 45%</div>
    <div class="mt-6 pt-4 border-t border-gray-800 border-dashed text-blue-300">
      <carbon:activity /> Llama.cpp backend: generating at 70 tok/s
    </div>
  </div>
</div>

</div>

<!--
Moje mašina není jen o chatu. Zatímco grafiky počítají kód pro agenta, procesor buildí monorepo v Rustu. Díky obrovské RAM mám všechna dočasná data v paměti. Je to uzavřený, bezpečný a extrémně rychlý ekosystém.
-->

---
transition: slide-up
layout: center
class: text-center
---

# Budoucnost: Kam dál? 🔮

<div class="flex justify-center gap-6 mt-12 text-left">

<div class="bg-gray-800/80 p-6 rounded-xl w-64 shadow-xl border-t-4 border-blue-500 hover:scale-105 transition-transform">
  <h3 class="mb-4 text-blue-400 flex items-center gap-2"><carbon:software-resource /> Software</h3>
  <ul class="list-none p-0 text-sm space-y-2">
    <li>🔹 Nativní RDNA 4 podpora pro vLLM</li>
    <li>🔹 TurboQuant & APEX</li>
  </ul>
</div>

<div class="bg-gray-800/80 p-6 rounded-xl w-64 shadow-xl border-t-4 border-green-500 hover:scale-105 transition-transform">
  <h3 class="mb-4 text-green-400 flex items-center gap-2"><carbon:chart-line /> Byznys</h3>
  <ul class="list-none p-0 text-sm space-y-2">
    <li>🔹 Měření ROI a návratnosti</li>
    <li>🔹 Produkční využití v projektech</li>
  </ul>
</div>

<div class="bg-gray-800/80 p-6 rounded-xl w-64 shadow-xl border-t-4 border-purple-500 hover:scale-105 transition-transform">
  <h3 class="mb-4 text-purple-400 flex items-center gap-2"><carbon:group /> Komunita</h3>
  <ul class="list-none p-0 text-sm space-y-2">
    <li>🔹 Inspirace: Mitko Vasilev a lokální AI scéna</li>
    <li>🔹 Sdílení know-how</li>
  </ul>
</div>

</div>

<!--
Jsme na začátku. Čekám na vLLM podporu, těším se na TurboQuant. Budu dál sbírat data a měřit, jak moc mi tahle investice šetří čas a peníze. Lokální AI je trend, který teprve začíná, a já jsem rád, že jsem do toho vlaku naskočil včas.
-->

---
layout: center
class: text-center
---

# Děkuji za pozornost! 🐆

<div class="text-2xl mt-4 text-gray-400">Máte otázky?</div>

<div class="mt-8 flex flex-col items-center gap-6">

  <a href="https://github.com/rozsival/panther-minor" target="_blank" class="block w-fit group no-underline !border-none !border-b-0 hover:!border-none">
    <div class="bg-gray-800/80 group-hover:bg-gray-700/80 transition-all flex flex-col items-center gap-4 px-8 py-6 rounded-2xl border border-gray-700 shadow-xl group-hover:border-blue-500/50 group-hover:scale-105 duration-300">
      <div class="bg-white p-2 rounded-xl shadow-inner border border-gray-200 inline-block pointer-events-none">
        <img src="https://api.qrserver.com/v1/create-qr-code/?size=140x140&data=https://github.com/rozsival/panther-minor" alt="QR Code Panther-Minor" class="w-[140px] h-[140px] rounded-sm m-0" />
      </div>
      <div class="flex items-center gap-3 mt-2">
        <carbon:logo-github class="text-2xl text-white" />
        <span class="font-mono text-gray-200 group-hover:text-white transition-colors">github.com/rozsival/panther-minor</span>
      </div>
    </div>
  </a>

  <div class="bg-gray-800/50 flex justify-center items-center gap-8 px-6 py-3 rounded-full border border-gray-700 max-w-fit mx-auto mt-2">
    <div class="flex items-center gap-2">
      <carbon:logo-github class="text-3xl hover:text-white transition-colors" />
      <span class="text-xl font-mono text-gray-300">@rozsival</span>
    </div>
    <div class="flex items-center gap-2">
      <carbon:logo-linkedin class="text-3xl text-blue-500 hover:text-blue-400 transition-colors" />
      <span class="text-xl font-mono text-blue-300">@vitrozsival</span>
    </div>
  </div>
  
</div>

<!--
Děkuji vám za pozornost. Pojďme se podívat na vaše dotazy.
-->
