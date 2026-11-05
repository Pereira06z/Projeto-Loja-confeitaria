📖 Sobre o projeto
O Forninho da Lili é uma confeitaria artesanal: coxinhas de morango, cookies e kits de presente, tudo feito sob encomenda e combinado pelo WhatsApp.

O projeto começou como uma landing page de uma página só e foi reorganizado como um site profissional, em duas partes que conversam entre si:

Para quem	O que faz
🍰 A vitrine	Clientes	Mostra o cardápio, explica como encomendar e leva direto ao WhatsApp com a mensagem pronta
🔐 Os bastidores	Só a Lili	Painel com login para cadastrar doces, registrar pedidos e acompanhar as vendas
O que a Lili muda no painel aparece no site na hora.

✨ Funcionalidades
Site do cliente
Páginas separadas: Início, Cardápio, Sobre Nós e Contato, com menu e rodapé iguais em todas
Vitrine animada: ao rolar a página, os doces se revezam um por vez, como numa vitrine de confeitaria
Cardápio com filtros por categoria (Docinhos, Cookies, Kits e presentes)
Aviso para alérgicos em cada doce
Encomenda em um toque: o botão abre o WhatsApp já com o nome do doce escrito
"Foto em breve" para doces sem foto e "Sob consulta" para itens sem preço fixo
Pensado primeiro para o celular, com botões grandes e cardápio em lista
Acessível: navegação por teclado, textos alternativos nas imagens e animações que respeitam quem pediu menos movimento no sistema
Funciona sem internet para as fontes e imagens (tudo está no projeto)
Cardápio com filtros por categoria e cartões de produto   Cardápio no celular

🔐 Painel administrativo
O painel não tem nenhum link no site. Ele só abre digitando o endereço com /admin no final, e pede usuário e senha.

Tela	O que a Lili faz
Login	Entra com usuário e senha. Sem login, qualquer página do painel volta para cá
Visão geral	Vê pedidos, itens vendidos e faturamento do mês, pedidos recentes e o que mais vende
Produtos	Cadastra, edita, desativa e exclui doces, com envio de foto pelo celular
Pedidos	Registra encomendas com vários itens, muda a situação (Novo → Em preparo → Pronto → Entregue) e vê o total
Clientes	Guarda quem já comprou, com atalho para o WhatsApp e para um novo pedido
Visão geral do painel com métricas do mês, pedidos recentes e vendas por item
Ver mais telas do painel
🧠 Decisões de projeto
Duas perguntas guiaram o painel: como a Lili adiciona um doce novo? e o que acontece quando ela para de fazer um doce?

Doce novo sem programador. Antes, cada produto era um bloco copiado à mão no HTML. Agora é um formulário: nome, preço, foto, salvar.
Desativar em vez de excluir. Um doce desativado sai do cardápio, mas continua nos pedidos antigos e pode voltar depois (ideal para doces de Páscoa e Natal).
Exclusão protegida. Produtos e clientes que já têm pedidos não podem ser apagados, para não perder o histórico de vendas.
Preço guardado na venda. Cada pedido registra o preço do dia. Se o preço mudar amanhã, o faturamento do mês passado continua certo.
Painel escondido. Sem link no site e com noindex, para não aparecer em buscadores.
Aviso explicando que um produto já vendido não pode ser excluído e oferecendo desativar
🗂️ Estrutura
Copiar
forninho-da-lili/
├── index.html · cardapio.html · sobre.html · contato.html · 404.html
├── assets/
│   ├── css/estilo.css        # visual do site
│   ├── fontes/               # Fraunces, Figtree e Dancing Script
│   ├── img/                  # logo, vitrine e fotos dos produtos
│   └── js/
│       ├── dados.js          # camada de dados (espelha as tabelas do SQLite)
│       └── cardapio.js       # monta o cardápio com os produtos ativos
├── admin/                    # painel (abre só por /admin)
│   ├── index.html            # login
│   ├── painel.html · produtos.html · pedidos.html · clientes.html
│   ├── produto-form.html · pedido-form.html · cliente-form.html
│   └── assets/               # admin.css e admin.js (proteção por login)
├── banco/
│   ├── 01_criar_tabelas.sql  # usuario, categoria, produto, cliente, pedido, pedido_item
│   └── 02_dados_exemplo.sql
├── docs/                     # prints e documentação do projeto
└── Dockerfile                # PHP 8.2 + Apache + SQLite


🗄️ Banco de dados
O modelo já está pronto para SQLite em banco/01_criar_tabelas.sql:

Copiar
usuario        categoria ──┐
                           ▼
cliente ──► pedido ──► pedido_item ◄── produto
Hoje, a versão de demonstração guarda os dados no navegador (localStorage), usando os mesmos nomes de tabelas e colunas do SQL. Assim, a troca para PHP + SQLite não muda as telas.

🚧 Próximos passos
Dividir a landing page em páginas
Separar a área administrativa em /admin com login
CRUD de produtos, pedidos e clientes
Modelo do banco SQLite
Integrar com PHP + SQLite (PDO, password_hash e sessões)
Publicar no Render com os dados no servidor
Carrinho: vários doces em uma única mensagem de WhatsApp
Criar categorias pelo painel
Fotos reais dos doces que ainda estão com "Foto em breve"
[!IMPORTANT] Esta é uma versão de demonstração. O login roda no navegador e os dados ficam só no aparelho em que foram cadastrados. A segurança de verdade (senha com hash e sessão no servidor) entra com a integração PHP + SQLite.

👥 Equipe
Projeto desenvolvido no curso de Análise e Desenvolvimento de Sistemas — SENAI.

Nome	GitHub
Gustavo Pereira	@Pereira06z
Matheus Augusto Ribeiro	@matheusaribeirodev
João Torres @joaotorresdev
Luis Neto  @luisneto016

