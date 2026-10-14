# 🏃‍♀️ ROTA — E-commerce de moda fitness lifestyle

> **Vitrine do projeto.** O código-fonte é privado por ser um projeto de cliente.

🔗 **[Ver a loja (demo)](https://rota-ecommerce.vercel.app)**

Loja própria da marca **ROTA**, de moda fitness para o dia a dia. O projeto tem vitrine com linha *lifestyle*, conta da cliente, painel de gestão e API própria. O **checkout e o pagamento são feitos pela Nuvemshop**, integrada por API e webhooks.

![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=flat&logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Sequelize](https://img.shields.io/badge/Sequelize-52B0E7?style=flat&logo=sequelize&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS_v4-06B6D4?style=flat&logo=tailwindcss&logoColor=white)
![Zod](https://img.shields.io/badge/Zod-3E67B1?style=flat&logo=zod&logoColor=white)
![Sentry](https://img.shields.io/badge/Sentry-362D59?style=flat&logo=sentry&logoColor=white)

## 🧩 Componentes

| Módulo | Descrição |
|---|---|
| **Loja** | React + Vite + Tailwind: catálogo, linha lifestyle, sacola, checkout e conta da cliente |
| **Painel** | React: produtos, variações, estoque, pedidos, cupons e usuários |
| **API** | Node.js + Express + Sequelize + PostgreSQL |

## ✨ Destaques

- Catálogo com filtros por categoria, ocasião e tamanho, ordenação e busca
- **Linha lifestyle por ocasião** (estúdio, cidade, noite), com looks que levam aos produtos
- Página de produto com galeria, cores, tamanhos, guia de medidas e "complete o look"
- Conta da cliente: pedidos, dados e recuperação de senha por e-mail
- Acompanhamento de pedido por código e e-mail

## 🔄 Integração com a Nuvemshop

```
Loja ── checkout ──▶ API ── pedido rascunho ──▶ Nuvemshop ── cliente paga
                      ▲                                │
                      └──────── webhook "pago" ────────┘
Painel ── "Enviado" + rastreio ──▶ API ──▶ Nuvemshop (avisa a cliente)
```

- O **painel é a fonte da verdade** do catálogo: produtos, preços, fotos e estoque são sincronizados com a Nuvemshop ao salvar
- A API reserva estoque e aplica cupons antes de redirecionar ao checkout
- Pedidos passam a "pago" automaticamente pelo webhook; envio e cancelamento também atualizam a Nuvemshop

## 🛡️ Qualidade

Validação com Zod, Helmet, rate limiting, upload de imagens com Sharp/S3, monitoramento com Sentry, migrations versionadas (Umzug) e testes automatizados da API.

---

Desenvolvido por **[Jolivan Abreu](https://github.com/JolivanAbreu)**.
