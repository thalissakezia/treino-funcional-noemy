# Treino funcional da Noemy

Site independente do treino do Flávio, baseado no mesmo layout: 6 dias de treino com ilustrações, progressão semanal, controles dos exercícios, histórico de pesagens e login por e-mail.

**Perfil usado para planejar os exercícios:** mulher, 53 anos, 1,60 m e 70,15 kg iniciais. Os treinos são sugestões para iniciante, com força leve, mobilidade, equilíbrio e caminhadas. Começar com 1 série e avançar se confortável. Em caso de sintomas ou doenças que limitem esforço, buscar avaliação profissional.

## Como publicar: só falta o ZIP e ativar o Pages

1. Baixe o arquivo **imagens-noemy.zip** fornecido no ChatGPT.
2. No repositório [treino-funcional-noemy](https://github.com/thalissakezia/treino-funcional-noemy), escolha **Add file → Upload files**, selecione o arquivo ZIP *sem extrair*, na raiz (ao lado do `index.html`) e toque em **Commit changes**. A automação `publicar-site.yml` extrai as 30 imagens dos exercícios e as 6 fichas ilustradas para a pasta `imagens/`. Não envie o ZIP antigo chamado `noemy_treino_repo_assets.zip`: ele tem nomes diferentes dos esperados pelo site.
3. Em **Settings → Pages → Build and deployment → Source**, selecione **GitHub Actions** (é uma configuração única). Depois, em **Actions**, veja a automação **Publicar site Noemy**. Se necessário, use **Run workflow**.
4. O endereço publicado será `https://thalissakezia.github.io/treino-funcional-noemy/`.

## Login e sincronização na nuvem

O site usa o projeto Supabase gratuito que já existe, com tabelas **exclusivas da Noemy**, separadas das tabelas do Flávio:

- `noemy_training_profile`
- `noemy_daily_weights`
- `noemy_exercise_progress`

As tabelas têm políticas RLS: cada conta vê apenas os próprios registros. Use um Gmail diferente para Noemy, e não compartilhe links de autenticação.

**Ação no Supabase:** em **Authentication → URL Configuration → Redirect URLs**, acrescente exatamente `https://thalissakezia.github.io/treino-funcional-noemy/**`. Mantenha a URL do Flávio, não substitua! O Site URL padrão pode permanecer o do Flávio pois o site da Noemy informa o `redirect_to` completo.

**Brevo:** não é necessária outra conta ou outra chave SMTP. A configuração de e-mail transacional existente é compartilhada pelo Supabase.

## Observações sobre as imagens

Todas as imagens são individualizadas e usam o personagem feminino da Noemy. A exibição mantém a imagem inteira, com as duas posições do movimento quando disponíveis. Algumas imagens de movimentos repetidos são reutilizadas em dias diferentes.

## Manutenção

Edite `index.html` e/ou as imagens sem alterar o repositório do Flávio. O código e as ilustrações são públicos; os registros pessoais de exercícios e pesos ficam no banco autenticado, não no GitHub.
