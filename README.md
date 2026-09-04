# Voleizinho da Mazela — Racha de Vôlei Online

## Arquivos
- index.html — aplicação completa
- logo_1.png — logo da tela de login e resumo final
- logo_2.png — logo das demais telas
- firestore.rules — regras do Firestore
- firebase-config.js — configuração de referência; o index.html já contém a configuração para evitar erro de arquivo ausente

## Publicação no GitHub Pages
Envie os arquivos diretamente para a raiz do repositório. Não coloque uma pasta dentro de outra.

No GitHub: Settings > Pages > Deploy from a branch > main > /(root).

## Firebase Authentication
Em Authentication > Sign-in method, habilite Email/Password.

Em Authentication > Settings > Authorized domains, adicione o domínio do GitHub Pages. Exemplo:
SEUUSUARIO.github.io

Se estiver usando um endereço personalizado, adicione também esse domínio.

## Firestore
Crie/abra o Firestore Database e publique o conteúdo de firestore.rules na aba Rules.

As regras atuais permitem:
- usuários autenticados consultarem e registrarem rachas;
- administradores gerenciarem usuários e excluírem histórico;
- usuário simples não acessar funções administrativas.

## Administrador principal
O e-mail pedrosajpo@gmail.com é reconhecido pelo aplicativo como administrador principal.

A primeira vez que esse administrador entrar, o aplicativo cria/atualiza o perfil dele em users/{UID}.

## Recuperação de senha
Na tela de login, informe o e-mail e toque em Recuperar senha. O Firebase envia o e-mail oficial de redefinição. Para funcionar pelo GitHub Pages, o domínio do site precisa estar em Authorized domains.

## Importante
A configuração Web do Firebase que aparece no código não substitui Security Rules. Nunca coloque senhas de usuários no GitHub. A senha fica no Firebase Authentication.
