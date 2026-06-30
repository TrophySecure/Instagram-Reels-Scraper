[Instagram Reels Scraper](https://apify.com/viralanalyzer/instagram-reels-scraper?fpr=data)

# 📸 Instagram Reels & Posts Scraper — Metrics & Engagement

> 🔗 [View on Apify Store](https://apify.com/viralanalyzer/instagram-reels-scraper) | 🇺🇸 English | 🇧🇷 Português

Extract **Instagram posts, Reels, and Carousels** with full engagement metrics. Get likes, comments, video views, hashtags, captions, and content type for any public profile. Playwright-based multi-strategy scraping with cookie seeding, API interception, embedded JSON parsing, and DOM extraction. No API key required.

## ✨ Features

- 📝 **Posts, Reels & Carousels** — Scrape all content types from public profiles
- 📊 **Full engagement metrics** — Likes, comments, video views, video duration
- 🏷️ **Hashtag extraction** — Automatic extraction from captions
- 🎬 **Content type detection** — Distinguishes Reels vs Posts vs Carousels
- 👥 **Multiple profiles** — Scrape several profiles in one run
- 🍪 **Cookie support** — Optionally provide cookies for authenticated access to private profiles
- 🔄 **4-strategy cascade** — API call, XHR interception, embedded JSON, DOM fallback
- 🛡️ **Stealth browsing** — Anti-detection with webdriver flag removal and fingerprint spoofing
- 🌐 **Residential proxy** — Built-in Apify residential proxy support (US)
- ✅ **Contract validation** — Every item checked against 11 required fields
- 🤝 **Co-author detection** — Identifies collaboration posts with multiple creators
- 📷 **Debug screenshots** — Saved to KV Store on failure for troubleshooting

## 📥 Input

| Parameter | Type | Required | Default | Description |
| --- | --- | --- | --- | --- |
| `profiles` | string[] | Yes | — | Instagram usernames to scrape (with or without @) |
| `maxPosts` | integer | No | 10 | Maximum posts to extract per profile (1-50) |
| `cookies` | object[] | No | — | Optional browser cookies for authenticated access. Array of {name, value, domain} objects |

### Input Example

```
{
  "profiles": ["cristiano", "leomessi", "neymarjr"],
  "maxPosts": 15
}
```

**With cookies for authenticated access:**

```
{
  "profiles": ["private_account"],
  "maxPosts": 10,
  "cookies": [
    {
      "name": "sessionid",
      "value": "your-session-id",
      "domain": ".instagram.com"
    }
  ]
}
```

## 📤 Output

| Field | Type | Description |
| --- | --- | --- |
| `id` | string | Instagram media ID |
| `shortCode` | string | Short code for the post URL |
| `url` | string | Full post URL ([https://www.instagram.com/p/{shortCode}/](https://www.instagram.com/p/%7BshortCode%7D/)) |
| `caption` | string | Full caption text |
| `timestamp` | string | ISO 8601 creation date |
| `likesCount` | integer | Number of likes |
| `commentsCount` | integer | Number of comments |
| `videoViewCount` | integer | Video view count (Reels and videos only, 0 for photos) |
| `videoDuration` | number | Video duration in seconds (0 for photos) |
| `hashtags` | string[] | Hashtags extracted from caption |
| `displayUrl` | string | Media display/thumbnail URL |
| `type` | string | Content type: "reel", "post", or "carousel" |
| `productType` | string | Instagram product type ("clips" for Reels, "feed" for posts) |
| `isVideo` | boolean | Whether the content is a video |
| `coauthors` | string[] | Co-author usernames for collaboration posts |
| `author` | string | Username of the scraped profile |
| `scrapedAt` | string | ISO 8601 timestamp of when the data was collected |

### Output Example

```
{
  "id": "3315678901234567890",
  "shortCode": "DFxRtPqWsYz",
  "url": "https://www.instagram.com/p/DFxRtPqWsYz/",
  "caption": "Another hat-trick! What a night at the Bernabeu. #football #cr7 #realmadrid #championsleague",
  "timestamp": "2026-02-28T21:45:00Z",
  "likesCount": 8542310,
  "commentsCount": 47823,
  "videoViewCount": 32150000,
  "videoDuration": 29.8,
  "hashtags": ["football", "cr7", "realmadrid", "championsleague"],
  "displayUrl": "https://scontent.cdninstagram.com/v/t51.2885-15/428573961_1234567890.jpg",
  "type": "reel",
  "productType": "clips",
  "isVideo": true,
  "coauthors": [],
  "author": "cristiano",
  "scrapedAt": "2026-03-06T15:30:00Z"
}
```

## 📋 Use Cases

- 📊 **Influencer Analytics** — Track engagement metrics across multiple influencers
- 🎯 **Content Strategy** — Analyze what types of content generate the most engagement
- 🏷️ **Hashtag Research** — Discover trending hashtags in your niche
- 🔍 **Competitor Monitoring** — Track competitor posting frequency and engagement rates
- 📈 **Campaign Tracking** — Measure influencer campaign performance over time
- 🔥 **Viral Content Detection** — Identify posts with unusually high engagement
- 👂 **Social Listening** — Monitor brand mentions and tagged content

## ❓ FAQ

**Q: Does the actor work without logging in to Instagram?**

A: Yes. The actor seeds session cookies by visiting instagram.com homepage first, then uses Instagram's web_profile_info API endpoint. No login or Instagram account is needed for public profiles.

**Q: Can I scrape private profiles?**

A: Only if you provide valid session cookies from an account that follows the private profile. Use the `cookies` input parameter with at least the `sessionid` cookie.

**Q: Why do some posts show 0 likes or 0 video views?**

A: If the primary API strategy fails and the actor falls back to DOM extraction (Strategy 4), posts will have URLs but no engagement metrics. The `_dataQuality` field will be set to "dom_only_no_metrics" in those cases.

**Q: What is the 4-strategy cascade?**

A: The actor tries four extraction methods in order: (1) API call with seeded cookies, (2) XHR interception during page navigation, (3) embedded JSON parsing from script tags, (4) DOM link extraction. Each successive strategy is a fallback if the previous one fails.

**Q: How many profiles can I scrape in one run?**

A: There is no hard limit on profiles, but each profile requires a separate browser session. The actor adds a 3-6 second delay between profiles to avoid rate limiting. For large batches, use residential proxy.

## 💰 Pricing

This actor uses **Pay Per Event (PPE)** pricing:

| Metric | Cost |
| --- | --- |
| `reel-scraped` | $0.04 per post/reel |

**Example**: Scraping 1,000 post/reels costs $40.00.

## 🔗 Related Actors

- [TikTok Viral Scanner](https://apify.com/viralanalyzer/tiktok-viral-scanner) — TikTok profile and video data
- [YouTube Fast Scraper](https://apify.com/viralanalyzer/youtube-fast-scraper) — YouTube video metrics
- [LinkedIn Intelligence](https://apify.com/viralanalyzer/linkedin-intelligence) — LinkedIn profiles and companies
- [Google Maps BR Scraper](https://apify.com/viralanalyzer/google-maps-br-scraper) — Google Maps business data

## 📝 Changelog

### v1.5 (Current)

- Cookie seeding phase — visits instagram.com to establish session cookies before scraping
- API-first strategy (web_profile_info endpoint with seeded cookies)
- XHR interception for GraphQL responses during page navigation
- Embedded JSON parsing (multiple patterns: __additionalDataLoaded, _sharedData, data-sjs)
- DOM fallback for post/reel link extraction
- Stealth browsing with webdriver flag removal and fingerprint spoofing
- Residential proxy support (US)
- User-provided cookies for authenticated access to private profiles
- Contract validation on every item (11 required fields)
- Debug screenshots saved to KV Store on failure
- Co-author detection for collaboration posts
- PPE billing via Actor.charge()

---

# 📸 Instagram Reels & Posts Scraper — Métricas e Engajamento

> 🇺🇸 English | 🇧🇷 Português

Extraia **posts, Reels e Carrosséis do Instagram** com métricas de engajamento completas. Obtenha curtidas, comentários, visualizações de vídeo, hashtags, legendas e tipo de conteúdo de qualquer perfil público. Scraping multi-estratégia com Playwright, cookie seeding, interceptação de API, parsing de JSON embutido e extração DOM. Sem necessidade de API key.

## ✨ Funcionalidades

- 📝 **Posts, Reels e Carrosséis** — Extraia todos os tipos de conteúdo de perfis públicos
- 📊 **Métricas de engajamento completas** — Curtidas, comentários, visualizações de vídeo, duração
- 🏷️ **Extração de hashtags** — Extração automática das legendas
- 🎬 **Detecção de tipo de conteúdo** — Distingue Reels vs Posts vs Carrosséis
- 👥 **Múltiplos perfis** — Extraia vários perfis em uma única execução
- 🍪 **Suporte a cookies** — Forneça cookies opcionais para acesso autenticado a perfis privados
- 🔄 **Cascata de 4 estratégias** — Chamada API, interceptação XHR, JSON embutido, fallback DOM
- 🛡️ **Navegação stealth** — Anti-detecção com remoção de flag webdriver e spoofing de fingerprint
- 🌐 **Proxy residencial** — Suporte integrado a proxy residencial Apify (US)
- ✅ **Validação de contrato** — Todo item verificado contra 11 campos obrigatórios
- 🤝 **Detecção de co-autores** — Identifica posts colaborativos com múltiplos criadores
- 📷 **Screenshots de debug** — Salvos no KV Store em caso de falha para troubleshooting

## 📥 Entrada

| Parâmetro | Tipo | Obrigatório | Padrão | Descrição |
| --- | --- | --- | --- | --- |
| `profiles` | string[] | Sim | — | Nomes de usuário do Instagram (com ou sem @) |
| `maxPosts` | inteiro | Não | 10 | Máximo de posts por perfil (1-50) |
| `cookies` | objeto[] | Não | — | Cookies opcionais para acesso autenticado. Array de objetos {name, value, domain} |

### Exemplo de Entrada

```
{
  "profiles": ["cristiano", "leomessi", "neymarjr"],
  "maxPosts": 15
}
```

**Com cookies para acesso autenticado:**

```
{
  "profiles": ["conta_privada"],
  "maxPosts": 10,
  "cookies": [
    {
      "name": "sessionid",
      "value": "seu-session-id",
      "domain": ".instagram.com"
    }
  ]
}
```

## 📤 Saída

| Campo | Tipo | Descrição |
| --- | --- | --- |
| `id` | string | ID da mídia no Instagram |
| `shortCode` | string | Código curto da URL do post |
| `url` | string | URL completa do post ([https://www.instagram.com/p/{shortCode}/](https://www.instagram.com/p/%7BshortCode%7D/)) |
| `caption` | string | Texto completo da legenda |
| `timestamp` | string | Data de criação ISO 8601 |
| `likesCount` | inteiro | Número de curtidas |
| `commentsCount` | inteiro | Número de comentários |
| `videoViewCount` | inteiro | Contagem de visualizações de vídeo (apenas Reels e vídeos, 0 para fotos) |
| `videoDuration` | número | Duração do vídeo em segundos (0 para fotos) |
| `hashtags` | string[] | Hashtags extraídas da legenda |
| `displayUrl` | string | URL da mídia/thumbnail |
| `type` | string | Tipo de conteúdo: "reel", "post" ou "carousel" |
| `productType` | string | Tipo de produto Instagram ("clips" para Reels, "feed" para posts) |
| `isVideo` | boolean | Se o conteúdo é vídeo |
| `coauthors` | string[] | Usernames de co-autores em posts colaborativos |
| `author` | string | Username do perfil extraído |
| `scrapedAt` | string | Timestamp ISO 8601 de quando os dados foram coletados |

### Exemplo de Saída

```
{
  "id": "3315678901234567890",
  "shortCode": "DFxRtPqWsYz",
  "url": "https://www.instagram.com/p/DFxRtPqWsYz/",
  "caption": "Another hat-trick! What a night at the Bernabeu. #football #cr7 #realmadrid #championsleague",
  "timestamp": "2026-02-28T21:45:00Z",
  "likesCount": 8542310,
  "commentsCount": 47823,
  "videoViewCount": 32150000,
  "videoDuration": 29.8,
  "hashtags": ["football", "cr7", "realmadrid", "championsleague"],
  "displayUrl": "https://scontent.cdninstagram.com/v/t51.2885-15/428573961_1234567890.jpg",
  "type": "reel",
  "productType": "clips",
  "isVideo": true,
  "coauthors": [],
  "author": "cristiano",
  "scrapedAt": "2026-03-06T15:30:00Z"
}
```

## 📋 Casos de Uso

- 📊 **Análise de Influenciadores** — Acompanhe métricas de engajamento de múltiplos influenciadores
- 🎯 **Estratégia de Conteúdo** — Analise quais tipos de conteúdo geram mais engajamento
- 🏷️ **Pesquisa de Hashtags** — Descubra hashtags em tendência no seu nicho
- 🔍 **Monitoramento de Concorrência** — Acompanhe frequência de postagem e taxas de engajamento
- 📈 **Rastreamento de Campanhas** — Meça performance de campanhas com influenciadores ao longo do tempo
- 🔥 **Detecção de Conteúdo Viral** — Identifique posts com engajamento excepcionalmente alto
- 👂 **Social Listening** — Monitore menções à marca e conteúdo marcado

## ❓ Perguntas Frequentes

**P: O actor funciona sem fazer login no Instagram?**

R: Sim. O actor semeia cookies de sessão visitando a homepage do instagram.com primeiro, depois usa o endpoint web_profile_info da API do Instagram. Nenhum login ou conta do Instagram é necessário para perfis públicos.

**P: Posso extrair dados de perfis privados?**

R: Apenas se você fornecer cookies de sessão válidos de uma conta que segue o perfil privado. Use o parâmetro de entrada `cookies` com pelo menos o cookie `sessionid`.

**P: Por que alguns posts mostram 0 curtidas ou 0 visualizações de vídeo?**

R: Se a estratégia primária de API falhar e o actor recorrer à extração DOM (Estratégia 4), os posts terão URLs mas sem métricas de engajamento. O campo `_dataQuality` será definido como "dom_only_no_metrics" nesses casos.

**P: O que é a cascata de 4 estratégias?**

R: O actor tenta quatro métodos de extração em ordem: (1) chamada API com cookies semeados, (2) interceptação XHR durante navegação da página, (3) parsing de JSON embutido de tags script, (4) extração de links DOM. Cada estratégia sucessiva é um fallback se a anterior falhar.

**P: Quantos perfis posso extrair em uma execução?**

R: Não há limite rígido de perfis, mas cada perfil requer uma sessão de browser separada. O actor adiciona um atraso de 3-6 segundos entre perfis para evitar rate limiting. Para grandes lotes, use proxy residencial.

## 💰 Preços

Este actor usa precificação **Pay Per Event (PPE)**:

| Métrica | Custo |
| --- | --- |
| Por post/reel extraído | $0.05 |

**Exemplo**: Extrair 3 perfis x 10 posts = 30 itens = $1.50.

## 🔗 Actors Relacionados

- [TikTok Viral Scanner](https://apify.com/viralanalyzer/tiktok-viral-scanner) — Dados de perfis e vídeos do TikTok
- [YouTube Fast Scraper](https://apify.com/viralanalyzer/youtube-fast-scraper) — Métricas do YouTube
- [LinkedIn Intelligence](https://apify.com/viralanalyzer/linkedin-intelligence) — Perfis e empresas LinkedIn
- [Google Maps BR Scraper](https://apify.com/viralanalyzer/google-maps-br-scraper) — Dados de empresas do Google Maps

## 📝 Changelog

### v1.5 (Atual)

- Fase de cookie seeding — visita instagram.com para estabelecer cookies de sessão antes do scraping
- Estratégia API-first (endpoint web_profile_info com cookies semeados)
- Interceptação XHR para respostas GraphQL durante navegação da página
- Parsing de JSON embutido (múltiplos padrões: __additionalDataLoaded, _sharedData, data-sjs)
- Fallback DOM para extração de links post/reel
- Navegação stealth com remoção de flag webdriver e spoofing de fingerprint
- Suporte a proxy residencial (US)
- Cookies do usuário para acesso autenticado a perfis privados
- Validação de contrato em cada item (11 campos obrigatórios)
- Screenshots de debug salvos no KV Store em caso de falha
- Detecção de co-autores em posts colaborativos
- Integração com cobrança PPE via Actor.charge()