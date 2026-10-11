# Plano de Design — Website Foco Clínica Dentária

## 1. Objetivo
Website institucional que apresenta a clínica como uma **visita guiada**: o visitante "chega" à clínica através de um vídeo narrado, conhece os espaços e os serviços, e termina com uma marcação de consulta simples.

**Metas principais**
- Gerar marcações (telefone, WhatsApp, formulário).
- Transmitir confiança, higiene e tecnologia.
- Facilitar a chegada à clínica (localização clara).

---

## 2. Identidade visual
| Elemento | Proposta |
|---|---|
| Conceito | "Foco" → precisão, clareza, atenção ao detalhe. Uso de um anel/círculo de foco (tipo lente) como elemento gráfico recorrente. |
| Cores | Azul petróleo `#0E5E6F` (principal), Verde-água `#3AAFA9` (destaque), Branco `#FFFFFF`, Cinza claro `#F4F7F8`, Grafite `#1F2A30` (texto). |
| Tipografia | Títulos: *Poppins* (600). Texto: *Inter* (400/500). |
| Fotografia | Luz natural, tons frios e limpos, pessoas reais (equipa e pacientes com autorização). |
| Ícones | Linha fina (ex.: Phosphor / Lucide), cantos arredondados. |
| Tom de voz | Próximo, calmo, profissional. Frases curtas. |

---

## 3. Vídeo de entrada (Hero) — "A caminho da Foco"

**Formato:** 60–90 s, 16:9 (desktop) + versão 9:16 (mobile), sem som por defeito com legendas; botão "Ativar narração". Botões **"Saltar vídeo"** e **"Marcar consulta"** sempre visíveis.

### Storyboard
| # | Cena | Duração | Imagem | Narração (exemplo) |
|---|---|---|---|---|
| 1 | Abertura | 0–5 s | Logótipo animado com efeito de "focagem" (desfocado → nítido). | "Bem-vindo à Foco Clínica Dentária." |
| 2 | Localização | 5–15 s | Plano aéreo (drone) da rua/zona da clínica. | "Estamos no coração de [bairro/cidade], fácil de encontrar." |
| 3 | Mapa rápido | 15–25 s | Mapa animado estilizado (cores da marca): pin da clínica + 3–5 pontos de referência (ex.: estação de metro/autocarro, farmácia, centro comercial, igreja/praça, estacionamento). Linha de percurso a desenhar-se até à porta. | "A 2 minutos da estação X, ao lado de Y, com estacionamento em Z." |
| 4 | Fachada e entrada | 25–32 s | Câmara aproxima-se da porta, que abre. | "Entre connosco." |
| 5 | Receção / Secretaria | 32–42 s | Plano contínuo (steadicam/gimbal) até ao balcão; rececionista sorri e cumprimenta. | "A nossa equipa recebe-o com atenção desde o primeiro momento." |
| 6 | Sala de espera | 42–52 s | Ambiente confortável: sofás, luz, revistas, água, Wi-Fi, espaço infantil (se houver). | "Um espaço tranquilo, pensado para o seu conforto." |
| 7 | Gabinetes / Sala de cirurgia | 52–72 s | Equipamento, esterilização, tecnologia (raio-X digital, scanner intraoral). Textos sobrepostos com os serviços. | "Gabinetes equipados com tecnologia moderna para implantologia, ortodontia, estética…" |
| 8 | Equipa + Fecho | 72–85 s | Equipa em grupo; logótipo + CTA. | "Foco no seu sorriso. Marque a sua consulta." |

**Produção**
- Filmagem: drone (autorização necessária), gimbal, luz natural + reforço LED.
- Mapa: animação em After Effects (ou Lottie para versão interativa no site).
- Narração: voz profissional em PT; legendas PT/EN.
- Música: biblioteca licenciada, calma e positiva.
- Entrega web: MP4 (H.264) + WebM, ≤ 8 MB por versão, imagem *poster* para carregamento rápido; `preload="metadata"`.

**Alternativa interativa (fase 2):** o scroll da página controla o vídeo/cenas ("scrollytelling"), cada cena revela a secção correspondente.

---

## 4. Estrutura da página inicial (one-page com âncoras)
A ordem das secções segue a narrativa do vídeo:

1. **Header fixo** — logótipo, menu (Localização · Clínica · Serviços · Equipa · Contactos), botão "Marcar consulta", telefone clicável.
2. **Hero com vídeo** — título "Foco no seu sorriso", subtítulo, CTAs.
3. **Como chegar**
   - Mapa interativo (Google Maps / Mapbox estilizado) com pin da clínica e pontos de referência com ícones.
   - Lista: transportes públicos, estacionamento, acessibilidade (rampa/elevador).
   - Botões "Abrir no Google Maps" / "Waze".
4. **A Clínica (tour)**
   - Cartões/galeria: Receção → Sala de espera → Gabinetes → Esterilização.
   - Opcional: tour virtual 360° (Matterport / Google Street View interior).
5. **Serviços** — grelha de cartões (ícone, nome, descrição curta, "Saber mais"):
   - Consulta e diagnóstico · Higiene oral · Dentisteria · Endodontia · Ortodontia (incl. alinhadores invisíveis) · Implantologia · Cirurgia oral · Prótese dentária · Estética (branqueamento, facetas) · Odontopediatria · Periodontologia.
   - Cada serviço com página própria: o que é, para quem, etapas, duração, FAQ, CTA.
6. **Equipa** — fotografia, nome, especialidade, nº da Ordem dos Médicos Dentistas.
7. **Porquê a Foco** — 3–4 diferenciais (tecnologia, horário alargado, acordos, primeira consulta).
8. **Testemunhos** — avaliações Google (com autorização/integração).
9. **Acordos e seguros** — logótipos de seguradoras/convenções.
10. **Contactos e marcação**
    - Formulário: nome, telefone, e-mail, serviço, data preferida, mensagem, consentimento RGPD.
    - Telefone, WhatsApp, e-mail, morada, horário.
11. **Rodapé** — morada, horários, redes sociais, Livro de Reclamações eletrónico, Política de Privacidade, Política de Cookies, licença ERS.

**Elementos fixos:** botão flutuante WhatsApp/telefone em mobile.

---

## 5. Páginas adicionais
- `/servicos/[servico]` — detalhe de cada serviço.
- `/equipa`
- `/marcacao` — formulário completo (ou integração com software de agenda).
- `/privacidade`, `/cookies`, `/termos`.
- (Opcional) `/blog` — dicas de saúde oral para SEO local.

---

## 6. Experiência e acessibilidade
- Mobile-first; vídeo vertical em telemóvel.
- Respeitar `prefers-reduced-motion` (mostrar imagem estática em vez de vídeo).
- Legendas no vídeo, contraste AA, navegação por teclado, textos alternativos.
- Tempo de carregamento < 2,5 s (LCP); vídeo carregado de forma diferida.

---

## 7. Stack técnica sugerida
- **Front-end:** Astro ou Next.js + Tailwind CSS (site estático rápido).
- **Animações:** GSAP (ScrollTrigger) para scrollytelling; Lottie para o mapa.
- **Mapa:** Mapbox GL ou Google Maps com estilo personalizado.
- **Formulários:** Formspree / Netlify Forms ou integração com software clínico.
- **Alojamento:** Vercel / Netlify; vídeo via CDN (ex.: Cloudflare Stream / Bunny).
- **SEO local:** Schema.org `Dentist`, Google Business Profile, meta tags, sitemap.
- **Analítica:** Plausible ou GA4 com consentimento de cookies.

---

## 8. Conteúdos a recolher junto da clínica
- [ ] Logótipo (vetorial) e cores existentes
- [ ] Morada exata e pontos de referência a destacar
- [ ] Lista final de serviços e textos/preços (se aplicável)
- [ ] Equipa: fotos, nomes, especialidades, nº OMD
- [ ] Horários, telefones, WhatsApp, e-mail, redes sociais
- [ ] Seguros/acordos
- [ ] Autorizações de imagem (equipa e pacientes)
- [ ] Dados legais: NIF, licença ERS, entidade responsável

---

## 9. Cronograma (estimativa)
| Fase | Atividades | Duração |
|---|---|---|
| 1. Descoberta | Briefing, recolha de conteúdos, referências | 1 semana |
| 2. Design | Wireframes → mockups (desktop/mobile) → aprovação | 2 semanas |
| 3. Vídeo | Guião, filmagem, mapa animado, narração, edição | 2–3 semanas (em paralelo com 2/4) |
| 4. Desenvolvimento | Implementação, formulários, mapa, SEO | 2–3 semanas |
| 5. Testes e lançamento | Testes multi-dispositivo, acessibilidade, performance, publicação | 1 semana |

**Total:** ~6–8 semanas.

---

## 10. Próximos passos
1. Validar este plano e a ordem da narrativa.
2. Confirmar pontos de referência para o mapa.
3. Criar wireframes da página inicial.
4. Agendar filmagem.
