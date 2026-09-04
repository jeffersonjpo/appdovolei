# Voleizinho da Mazela — versão online

## Arquivos para o GitHub Pages
- `index.html`
- `firebase-config.js`
- `firestore.rules`
- `logo_1.png`
- `logo_2.png`

## Firebase
O projeto já está apontado para o Firebase informado no pedido.

### Authentication
Ative o provedor **Email/Password** em:
Firebase Console → Authentication → Sign-in method → Email/Password.

O administrador principal é reconhecido pelo e-mail:
`pedrosajpo@gmail.com`

Como esse usuário já foi criado no Firebase Authentication, basta entrar com o e-mail e senha cadastrados.

### Firestore
Crie o banco Firestore se ainda não existir e publique as regras do arquivo `firestore.rules`.

A estrutura usada é:
- `users/{uid}` — nome, e-mail, nível (`admin` ou `user`)
- `racha/current` — racha em andamento compartilhado entre os aparelhos
- `racha/data/archives/{id}` — rachas finalizados/arquivados

### Importante sobre criação de usuários
O administrador cria novos usuários dentro do próprio sistema usando uma segunda instância do Firebase Authentication. Isso permite cadastrar e-mail + senha sem desconectar o administrador principal.

O Firebase não envia a senha inicial para o novo usuário. A senha informada pelo administrador é usada para criar a conta. O usuário pode utilizar **Recuperar senha** na tela de login para receber o e-mail seguro de redefinição do Firebase.

### Remoção de usuários
O painel remove o perfil de acesso da coleção `users`. A conta de autenticação (Firebase Authentication) não pode ser excluída com segurança pelo navegador sem o Admin SDK / Cloud Functions. Para excluir definitivamente a conta de login, use o Console do Firebase.

### Publicação no GitHub Pages
1. Crie um repositório no GitHub.
2. Envie os cinco arquivos para a raiz do repositório.
3. Vá em **Settings → Pages**.
4. Em **Build and deployment**, selecione **Deploy from a branch**.
5. Escolha `main` e `/ (root)`.
6. Salve e aguarde a publicação.

## Funções de acesso
### Administrador
- Registrar rachas
- Consultar ranking e histórico
- Adicionar administradores e usuários simples
- Remover perfis de usuário
- Excluir rachas
- Apagar todo o histórico (o ranking é recalculado e zera)
- Exportar e importar backup

### Usuário simples
- Registrar o racha
- Consultar ranking
- Consultar histórico
- Visualizar resumo final
- Não vê o menu Administração, backup ou exclusão de histórico

## Logos
- `logo_1.png`: tela de login e resumo final.
- `logo_2.png`: cabeçalho das demais telas.
As logos usam `object-fit: contain` e área reservada para evitar cortes.
