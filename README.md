# Calculadora de Pisos — pacote para compartilhamento

Pacote da calculadora web atual, preservando a interface, o layout, os estilos, os componentes e as funcionalidades existentes.

## Requisitos

- Conta no GitHub;
- Conta na Vercel;
- Navegador moderno com JavaScript habilitado;
- Supabase: opcional na versão atual.

A calculadora é estática, não exige Node.js, banco de dados ou variáveis de ambiente para funcionar. Os modelos personalizados ficam salvos no armazenamento local do navegador e, portanto, não são sincronizados entre dispositivos.

## Teste local

Abra `index.html` diretamente no navegador. Para uma simulação mais próxima da hospedagem, publique o projeto na Vercel ou use qualquer servidor estático local.

## Publicação pelo GitHub e Vercel

1. Crie um repositório novo no GitHub.
2. Envie para o repositório o conteúdo deste pacote, mantendo `index.html` na raiz.
3. No painel da Vercel, selecione **Add New → Project**.
4. Importe o repositório do GitHub.
5. Como é um site estático, deixe o framework como **Other** ou sem framework.
6. Não informe comando de build nem diretório de saída; a configuração `vercel.json` já direciona as rotas para a calculadora.
7. Clique em **Deploy** e abra o domínio fornecido pela Vercel.
8. Para atualizações, faça novo push no GitHub; a Vercel fará novo deploy automaticamente.

## Supabase

A versão atual não depende do Supabase. Consulte `supabase/README.md` se for necessário sincronizar modelos personalizados entre usuários ou dispositivos. Essa evolução exige integração de código, tabela, autenticação e políticas de segurança, e não foi ativada para evitar alterações desnecessárias.

## Desafios esperados e soluções

- **Modelos não aparecem em outro dispositivo:** o armazenamento atual é local ao navegador. Cadastre novamente ou implemente a integração opcional com Supabase.
- **Página não abre após publicação:** confirme que `index.html` está na raiz do repositório e que o projeto foi publicado como site estático.
- **Alterações não aparecem:** aguarde o novo deploy e atualize a página sem usar o cache; confira o último deployment na Vercel.
- **Cadastro parece perdido:** evitar modo anônimo e limpeza dos dados do navegador; os modelos personalizados dependem do `localStorage`.
- **Layout no celular:** teste Chrome, Safari, Edge e Firefox em larguras diferentes; mantenha o zoom do navegador em 100%.
- **Erro de segurança no Supabase:** nunca use a chave `service_role` no front-end e revise as políticas RLS antes de liberar a integração.

## Checklist antes de compartilhar

- [ ] `index.html` está na raiz do repositório;
- [ ] O cálculo de materiais funciona;
- [ ] Impressão e limpeza funcionam;
- [ ] Cadastro, edição e exclusão de modelos funcionam;
- [ ] A visualização móvel foi conferida;
- [ ] Nenhuma chave privada foi commitada no GitHub.
