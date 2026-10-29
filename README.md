# FitNutri — versão 0.3

Aplicativo web responsivo em português para diário alimentar, calorias/macronutrientes, hidratação, metas e histórico de peso. Feito com HTML, CSS e JavaScript sem dependências externas.

## Testar no Windows

1. Extraia o ZIP para uma pasta, por exemplo `C:\FitNutri`.
2. Abra `index.html` no Chrome ou Edge. O diário, as metas, a água e o peso funcionam localmente.
3. Os dados ficam no armazenamento local do navegador. Evite limpar os dados do site se quiser preservá-los.

Para testar a instalação PWA e o modo offline, sirva a pasta por HTTP local. Se tiver Python instalado, abra o Prompt de Comando nessa pasta e rode:

```bash
python -m http.server 8000
```

Depois acesse `http://localhost:8000` no Chrome/Edge. No Edge, use o menu Aplicativos para instalar o site como aplicativo. A abertura direta do arquivo funciona para testar, mas service worker/PWA requer HTTP ou HTTPS.

## Android

Para instalar como PWA no Android, publique os arquivos em uma hospedagem HTTPS (por exemplo, GitHub Pages) e abra o endereço no Chrome Android; no menu, escolha **Instalar app** ou **Adicionar à tela inicial**. O PWA exige HTTPS, exceto localhost.

## O que já funciona

- Registro e exclusão de alimentos para o dia atual.
- Estimativa de kcal, proteínas, carboidratos e gorduras pela porção em gramas.
- Filtro por refeição.
- Metas diárias editáveis.
- Registro de copos de água por dia.
- Registro e histórico recente de peso.
- Exportação e importação de backup JSON para proteger e transferir dados entre navegadores/dispositivos.
- Persistência local com `localStorage`.
- Layout adaptável para desktop e celular e arquivos básicos de PWA.

## Limites da versão 0.3

- Banco inicial de alimentos de demonstração, com valores aproximados por 100 g.
- Cadastro e exclusão de alimentos personalizados, com kcal, proteínas, carboidratos e gorduras por 100 g.
- Os alimentos personalizados são salvos no dispositivo e incluídos no backup JSON.
- Sem contas, sincronização na nuvem, leitor de código de barras, análise de fotos ou prescrição nutricional. Os valores dos alimentos precisam ser conferidos pelo usuário em rótulos ou fontes nutricionais confiáveis.
- Metas iniciais são exemplos e não substituem avaliação individual por nutricionista.


## Backup

Use **Exportar meus dados** para baixar um arquivo JSON. Para restaurar, clique em **Importar backup** e selecione um arquivo exportado pelo FitNutri. A importação substitui os dados atuais após confirmação; exporte um backup antes de importar.


## Cadastrar um alimento personalizado

1. Clique em **Adicionar alimento**.
2. Escolha **Cadastrar alimento personalizado**.
3. Informe o nome e os valores nutricionais **por 100 g**.
4. Clique em **Salvar alimento**. Ele ficará disponível na lista para registrar porções no diário.
5. Para excluir um alimento personalizado da lista, abra **Meus alimentos personalizados** no mesmo diálogo. Os registros já lançados no diário não são apagados.

O backup da versão 0.3 inclui os alimentos personalizados. Backups antigos da versão 0.2 continuam aceitos; como não tinham esse campo, não irão criar alimentos personalizados automaticamente.
