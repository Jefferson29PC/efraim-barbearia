# Efraim Barbearia — aplicativo de agendamento

Aplicativo web (instalável no celular) da Efraim Barbearia, mantido pelo Ateliê Web.

- **Clientes:** cadastro com CPF e senha própria, agendamento com antecedência mínima, remarcação, Cartão Fidelidade, Indique um amigo, chat com a barbearia e jogo de corrida.
- **Painel Administrativo:** agenda, Kanban, mensagens, avisos com voz, base de clientes (com planilha), caixa do dia, dashboard e ajustes de serviços, preços e horários.

## Arquivos

| Arquivo | Para que serve |
|---|---|
| `index.html` | O aplicativo inteiro |
| `firebase-config.js` | Chaves do projeto Firebase (não são senhas) |
| `firestore.rules` | Regras de segurança do banco de dados |
| `manifest.webmanifest`, `sw.js`, `icons/` | Deixam o app instalável no celular |

## Endereços

- Clientes: `https://jefferson29pc.github.io/efraim-barbearia/`
- Administrador: o mesmo endereço com `#admin` no final. Esse link não aparece para os clientes.

## Configuração (feita uma vez)

1. **Firebase:** Authentication com o método **Anônimo** ativo, e Firestore criado em `southamerica-east1`.
2. **Regras:** copie o conteúdo de `firestore.rules` em *Firestore Database → Regras* e toque em **Publicar**.
3. **Chaves:** preencha `firebase-config.js` com o bloco `firebaseConfig` do projeto.
4. **GitHub Pages:** *Settings → Pages → Branch `main` / pasta `/ (root)` → Save*.
5. **Primeiro acesso do administrador:** abra o endereço com `#admin` e crie o usuário e a senha **logo depois de publicar**. Só o primeiro acesso cria o login.

## Suporte

- **Cliente esqueceu a senha:** no painel, aba *Base de clientes*, toque em **Redefinir senha** no cliente e mande a senha provisória pelo WhatsApp. O cliente troca depois em *Trocar senha*.
- **Administrador esqueceu a senha:** no Firebase, em *Firestore Database → Dados*, apague o documento `config/admin`, os documentos da coleção `sessoesAdmin` e o campo `adminCriado` de `config/publico`. Depois abra o endereço `#admin` e crie o acesso de novo.
- **Trocar a senha do administrador:** no painel, aba *Hoje*, em *Usuário e senha do Painel Administrativo*. Os outros aparelhos precisam entrar de novo.

## Segurança e privacidade (LGPD)

- Cada cliente só consegue ler os próprios dados. A base completa, o caixa e o chat de todos ficam visíveis só para o administrador.
- As senhas ficam guardadas apenas em forma de código (hash) e ninguém consegue lê-las, nem o administrador.
- Os horários ocupados e o ranking do jogo não mostram CPF.
- O cadastro exige o aceite da Política de Privacidade, e a data do aceite fica registrada.
- Plano gratuito do Firebase (Spark): sem custo para o volume de uma barbearia.
