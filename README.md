# Treino funcional da Noemy

Site independente do [Treino do Flávio](https://github.com/thalissakezia/treino-funcional-flavio), com treinos ilustrados de segunda a sábado, acompanhamento das semanas, peso diário, login por Gmail e sincronização.

**Perfil inicial:** mulher, 53 anos, 1,60 m, 70,15 kg. A proposta é começar com intensidade leve, sem saltos, priorizando força, mobilidade, equilíbrio e caminhada. O site exibe adaptações para a semana 1 e progressão gradual.

## Estrutura organizada

- `index.html`: site principal, com programa, instruções e interface.
- `imagens/`: as **30 imagens de exercícios**, **6 guias ilustrados** e ilustração de espera. O site carrega diretamente desta pasta.
- `fontes-ilustracoes/`: arquivos PNG originais preservados para futuras edições (não entram na publicação).
- `plano_treino_noemy.json`: arquivo recebido como referência de planejamento; o programa efetivamente usado está no `index.html`.
- `.github/workflows/publicar-site.yml`: verifica a existência das 36 imagens e publica automaticamente.

**Não é preciso enviar outro ZIP.** Os arquivos já estão organizados no repositório.

## Falta ativar GitHub Pages

A ação de publicação executou a validação dos arquivos, mas a etapa **Configurar GitHub Pages** não pôde prosseguir porque o Pages deste repositório ainda não está habilitado.

1. Abra [Settings → Pages](https://github.com/thalissakezia/treino-funcional-noemy/settings/pages).
2. Em **Build and deployment → Source**, selecione **GitHub Actions**. Salve, se aparecer o botão.
3. Se não publicar automaticamente, abra [Actions](https://github.com/thalissakezia/treino-funcional-noemy/actions/workflows/publicar-site.yml) e execute **Run workflow**.

Após a publicação, o endereço será **https://thalissakezia.github.io/treino-funcional-noemy/**.

## Login e sincronização privados

O Supabase existente já possui tabelas separadas, com políticas de acesso por usuário:

- `noemy_training_profile`
- `noemy_daily_weights`
- `noemy_exercise_progress`

Não é preciso criar outro projeto Supabase nem nova conta no Brevo. No Supabase, em **Authentication → URL Configuration → Redirect URLs**, **adicione**:

`https://thalissakezia.github.io/treino-funcional-noemy/**`

Não apague a URL do Flávio. O site informa o endereço completo da Noemy ao solicitar o link de login. A pessoa usa o próprio e-mail, sem misturar os registros do Flávio.

**Segurança:** nunca publique tokens, links de login, chaves secretas ou dados pessoais no repositório público. O histórico de peso é guardado no dispositivo e, quando conectado, sincronizado com as tabelas privadas.

## Cuidados

Para uma pessoa que inicia atividade física aos 53 anos, respeite o condicionamento. Em caso de sintomas, doenças ou limitações, procure avaliação profissional. Não existe garantia de perda de peso específica, definição ou ausência de flacidez em 30 dias.
