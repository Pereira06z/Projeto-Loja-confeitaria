🍓 Forninho da Lili

Confeitaria artesanal | Site institucional e painel administrativo

O Forninho da Lili é um projeto de site para uma confeitaria artesanal especializada em coxinhas de morango, cookies e kits para presente. Todos os produtos são feitos sob encomenda, com atendimento e confirmação dos pedidos diretamente pelo WhatsApp.

O projeto começou como uma landing page de uma única página e evoluiu para uma aplicação web organizada em duas áreas integradas: uma vitrine digital para os clientes e um painel administrativo exclusivo para a gestão da confeitaria.

📖 Sobre o projeto

O sistema foi desenvolvido para facilitar tanto a experiência de compra dos clientes quanto o gerenciamento diário da confeitaria.

Área	Público	Funcionalidade
🍰 Vitrine	Clientes	Apresenta os produtos, informações da confeitaria e direciona os clientes para o WhatsApp com mensagens personalizadas.
🔐 Painel administrativo	Lili	Permite gerenciar produtos, registrar pedidos, cadastrar clientes e acompanhar as vendas.

As alterações realizadas no painel administrativo são refletidas na vitrine, mantendo o cardápio atualizado.

✨ Funcionalidades
🍰 Site do cliente
Páginas independentes: Início, Cardápio, Sobre Nós e Contato.
Navegação padronizada: menu e rodapé compartilhados entre as páginas.
Vitrine animada: apresentação dos doces com animações durante a rolagem da página.
Cardápio dinâmico: produtos organizados por categorias.
Filtros por categoria: Docinhos, Cookies, Kits e Presentes.
Informações sobre alergênicos: avisos individuais em cada produto.
Encomenda pelo WhatsApp: botão que abre uma conversa com o nome do produto preenchido.
Produtos sem imagem: exibição de "Foto em breve".
Produtos sem preço fixo: indicação de "Sob consulta".
Design responsivo: desenvolvido com foco inicial em dispositivos móveis.
Acessibilidade: navegação por teclado, textos alternativos nas imagens e respeito à preferência por redução de movimento.
Recursos locais: fontes e imagens armazenadas no próprio projeto.
🔐 Painel administrativo

O painel administrativo é uma área exclusiva, acessada pelo endereço /admin, sem link de acesso na navegação pública do site.

Tela	Funcionalidades
Login	Autenticação com usuário e senha.
Visão geral	Acompanhamento de pedidos, produtos vendidos, faturamento mensal e itens mais vendidos.
Produtos	Cadastro, edição, desativação e exclusão de produtos, com envio de fotos.
Pedidos	Registro de encomendas com vários produtos, cálculo do total e atualização de status.
Clientes	Cadastro e consulta de clientes, com atalhos para WhatsApp e criação de novos pedidos.

Fluxo de status dos pedidos:

Novo → Em preparo → Pronto → Entregue

🧠 Decisões de projeto

Durante o desenvolvimento, algumas decisões foram tomadas para facilitar a utilização e garantir a organização das informações.

1. Cadastro de produtos sem precisar programar

Anteriormente, cada produto precisava ser adicionado manualmente ao HTML. Agora, a Lili pode cadastrar novos doces diretamente pelo painel administrativo, preenchendo informações como nome, preço e foto.

2. Desativação de produtos

Em vez de excluir um produto temporariamente, é possível desativá-lo.

Dessa forma, ele deixa de aparecer no cardápio público, mas continua registrado no histórico de pedidos e pode ser reativado posteriormente.

Essa funcionalidade é especialmente útil para produtos sazonais, como doces de Páscoa e Natal.

3. Exclusão protegida

Produtos e clientes vinculados a pedidos existentes não podem ser excluídos, evitando a perda de informações importantes do histórico de vendas.

4. Histórico de preços

Cada pedido registra o preço do produto no momento da venda. Assim, alterações futuras nos valores não modificam o faturamento de períodos anteriores.


🗄️ Banco de dados

O projeto possui uma estrutura de banco de dados planejada para SQLite, com criação das tabelas disponível em:

banco/01_criar_tabelas.sql

Modelo de dados

O banco contempla as seguintes entidades:

usuario: dados dos usuários administrativos.
categoria: categorias dos produtos.
produto: informações dos doces disponíveis.
cliente: cadastro dos clientes.
pedido: registro das encomendas.
pedido_item: produtos e valores vinculados a cada pedido.

Relacionamentos principais:

text
usuario

categoria ──────┐
                ▼
cliente ───► pedido ───► pedido_item ◄─── produto


Atualmente, a versão demonstrativa utiliza localStorage para armazenar os dados diretamente no navegador, mantendo uma estrutura compatível com os nomes das tabelas e colunas planejadas para o SQLite.

Essa organização facilita uma futura migração para PHP e SQLite sem exigir grandes alterações nas telas.

🚧 Próximos passos

As seguintes melhorias estão planejadas para as próximas versões:

Finalizar a divisão da landing page em páginas independentes.
Consolidar a área administrativa em /admin com autenticação.
Finalizar o CRUD de produtos, pedidos e clientes.
Implementar a integração com PHP e SQLite.
Implementar autenticação segura utilizando password_hash() e sessões PHP.
Publicar o projeto com persistência de dados no servidor.
Desenvolver um carrinho para adicionar vários doces em uma única mensagem de WhatsApp.
Permitir a criação de categorias diretamente pelo painel.
Adicionar fotos reais dos produtos que ainda estão identificados como "Foto em breve".
⚠️ Observação sobre a versão demonstrativa

Esta versão possui algumas limitações importantes:

O login é realizado no próprio navegador.
Os dados são armazenados no localStorage.
As informações ficam restritas ao navegador e ao dispositivo em que foram cadastradas.
A autenticação ainda não possui validação de sessão no servidor.

A implementação de segurança real, com PHP, SQLite, senhas protegidas por hash e sessões no servidor, está prevista para uma próxima etapa do desenvolvimento.

Esta versão tem como objetivo demonstrar a interface, as funcionalidades e a estrutura planejada para o sistema.

👥 Equipe de desenvolvimento

Projeto desenvolvido como parte do curso de Análise e Desenvolvimento de Sistemas — SENAI.

-Matheus Augusto Ribeiro	@matheusaribeirodev
-Gustavo Pereira	@Pereira06z
-Luis Neto	@luisneto016
-João Torres	@joaotorresdev

<p align="center">
🍓 <strong>Forninho da Lili</strong><br>
Feito com carinho, criatividade e tecnologia.
</p>
