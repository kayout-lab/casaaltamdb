# CASA ALTA — V4

Sistema web de cadastro de empreendimentos conectado ao Supabase e pronto para publicação no GitHub Pages.

## Arquivos

- `index.html` — aplicação completa (interface, login, cadastro, relatórios e gráficos)
- `config.js` — coloque aqui a URL e a chave pública do Supabase
- `config.example.js` — modelo do `config.js`
- `supabase_schema_seed.sql` — cria as tabelas, RLS, permissões e importa a base inicial
- `base_importacao.csv` — referência da base utilizada na carga inicial

## Recursos V4

- Login por e-mail e senha
- Seleção obrigatória do empreendimento antes do acesso operacional
- Visão corporativa com todos os empreendimentos juntos, apenas de forma agregada
- Cadastro e edição de empreendimentos
- Cadastro e edição de unidades/vendas no contexto do empreendimento selecionado
- Relatórios por empreendimento
- Relatório executivo consolidado
- Filtros, indicadores, rankings, gráficos e exportação CSV
- Impressão do relatório
- RLS para restringir acesso aos usuários autenticados

## Configuração

1. Crie um projeto no Supabase.
2. Abra `SQL Editor` e execute todo o conteúdo de `supabase_schema_seed.sql`.
3. Em `Authentication > Users`, crie o primeiro usuário.
4. Em `Project Settings > API`, copie a `Project URL` e a chave pública/publicável.
5. Edite `config.js`:

```js
window.APP_CONFIG = {
  SUPABASE_URL: 'https://SEU-PROJETO.supabase.co',
  SUPABASE_ANON_KEY: 'SUA_CHAVE_PUBLICAVEL'
};
```

6. No GitHub, crie um repositório e envie os arquivos do projeto.
7. Ative `Settings > Pages > Deploy from a branch > main / root`.

## Segurança

Nunca coloque `service_role`, chave secreta ou senha do banco no `index.html` ou `config.js`.

A aplicação usa a chave pública do Supabase no navegador e as políticas RLS do banco para proteger os dados.
