# MAXX Pet Shop — Site Institucional

Website profissional, responsivo e animado para a **MAXX Pet Shop**, localizada em Santa Terezinha, São Bernardo do Campo.

## 📌 Informações da Empresa

- **Nome:** MAXX Pet Shop
- **Avaliação Google:** 4,7 ★ (105 avaliações)
- **Endereço:** R. Tiradentes, 508 — Santa Terezinha, São Bernardo do Campo — SP, 09710-193
- **WhatsApp / Telefone:** (11) 99145-3280 — link direto: `wa.me/5511991453280`
- **Site oficial:** maxxpetshop.com
- **Horário:** Segunda a sábado · 09:00 às 17:30
- **Volume:** 600+ atendimentos por mês (todas as unidades)
- **Diferenciais:**
  - Banho e tosa com cuidado excelente
  - Equipe atenciosa e carinhosa
  - Adriane & equipe — destaque em tosa
  - Empresa de empreendedoras
  - Comunidade LGBTQ+ friendly

## 🛠 Stack

- HTML5 semântico + ARIA
- CSS3 com design system via custom properties (mobile-first, 2 breakpoints)
- JavaScript vanilla + **GSAP 3.12** + ScrollTrigger
- Google Fonts (Outfit, Plus Jakarta Sans, JetBrains Mono)
- 100% estático, sem build step

## 🎨 Design System

| Token        | Valor      | Uso                          |
| ------------ | ---------- | ---------------------------- |
| `--bg`       | `#FAF7F2`  | Fundo principal (linen)      |
| `--surface`  | `#FFFFFF`  | Cards e seções alternadas    |
| `--ink`      | `#0F172A`  | Texto principal              |
| `--muted`    | `#64748B`  | Texto secundário             |
| `--brand`    | `#0F766E`  | Teal (confiança, saúde)      |
| `--accent`   | `#F59E0B`  | Amber (calor humano, estrelas) |
| `--border`   | `#E2E8F0`  | Divisores sutis              |

**Tipografia:** Outfit (display), Plus Jakarta Sans (texto), JetBrains Mono (eyebrows).

## ✨ Animações (GSAP)

- **Hero entrance** — stagger de eyebrow → H1 → lede → CTAs → tags
- **Hero SVG draw** — paths animados via `stroke-dashoffset`
- **ScrollTrigger reveals** — toda seção com `data-reveal` ganha `y: 28, opacity: 0` ao entrar (start 88%, `once: true`)
- **KPI counter** — `gsap.to()` com `onUpdate` para animar números (4,7 / 600+ / 105 / 5+)
- **Service card hover** — lift de 6px via GSAP (sem reflow)
- **WhatsApp FAB pulse** — `yoyo: true` infinito, **pausa em `visibilitychange`**
- **Paw deco parallax** — `scrub: 1` sutil
- **Reduced-motion** — respeitado via `matchMedia`; estado final imediato

**Performance (alinhado a `gsap-performance`):**
- Apenas `transform` + `opacity` (nunca `width`/`top`)
- `will-change: transform` apenas em `.hero-graphic` e `.whatsapp-fab`
- `stagger` em vez de tweens manuais
- `ScrollTrigger.refresh()` apenas após fontes (debounce natural)
- `overwrite: 'auto'` nos hovers

## 📁 Estrutura

```
maxx-pet/
├── index.html        single-page com 7 seções
├── css/
│   └── styles.css    design system + layout + responsivo
├── js/
│   └── main.js       GSAP entrance, reveals, KPIs, FAB, menu
├── assets/
│   ├── logo.svg       marca (pata + wordmark)
│   ├── hero.svg       composição vetorial do cachorro
│   ├── og.svg         capa Open Graph
│   └── icon-*.svg     ícones de serviços e contato
└── README.md
```

## 🌍 Seções

1. **Header sticky** com menu mobile hambúrguer
2. **Hero** — H1 com ênfase em *carinho* / *ama*, badge 4,7★, ilustração SVG vetorial
3. **Serviços** — Banho, Tosa da raça, Tosa higiênica, Veterinário (4 cards)
4. **Sobre** — história, valores (LGBTQ+ friendly, empreendedoras), quote da Adriane
5. **Números** — 4 KPIs animados
6. **Depoimentos** — Nicole Silva, Luis Henrique Galvão + citação curada
7. **Localização & Contato** — endereço, telefone, horário, mapa Google embed
8. **CTA final** — bloco WhatsApp
9. **Footer** + **FAB WhatsApp** flutuante com pulse

## ▶️ Como Executar

Basta abrir o `index.html` no navegador, ou servir localmente:

```bash
# Python
python -m http.server 8000

# Node
npx serve .
```

Acesse `http://localhost:8000`.

## 🔍 Verificação recomendada

1. Responsivo em 375 / 768 / 1280 px
2. Botão WhatsApp abre `wa.me/5511991453280`
3. DevTools → Performance → 60fps durante scroll
4. Lighthouse mobile: Performance ≥ 95, Acessibilidade ≥ 95
5. `prefers-reduced-motion: reduce` desativa animações

## 📄 Licença

Conteúdo e copy pertencem à MAXX Pet Shop. Código pode ser reutilizado como referência.
