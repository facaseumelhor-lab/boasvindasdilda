# Boas Práticas para Publicação no GitHub & GitHub Pages

Este guia descreve a estrutura de organização de arquivos e os passos recomendados para publicar e manter o portal de **Boas-Vindas da Marisa Dilda Seguros** no GitHub de forma profissional, segura e eficiente.

---

## 1. Organização da Estrutura de Arquivos

Para manter o projeto limpo e fácil de carregar, utilize a seguinte estrutura padrão:

```
Boas Vindas MD/
├── index.html            # Página principal (deve ter esse nome exato)
├── .gitignore            # Arquivo para ignorar arquivos desnecessários
├── GITHUB_GUIDE.md       # Este guia de documentação
├── boasvindas.md         # Template de mensagem para transportadoras
└── images/               # Pasta centralizada para todas as imagens e logotipos
    ├── logodilda10.png
    └── ...
```

### Regras de Organização:
- **`index.html` na Raiz**: O GitHub Pages exige que o arquivo de entrada principal seja chamado `index.html` e esteja na pasta raiz (ou na pasta `/docs`) para servir a página web automaticamente.
- **Pasta de Assets (`images/`)**: Nunca deixe arquivos de imagens soltos na raiz. Mantenha todas as mídias dentro de uma subpasta dedicada.
- **Nomes de Arquivos**: Use apenas letras minúsculas, números e hífens (`-`) ou underscores (`_`) para nomes de arquivos (ex: `logodilda10.png` em vez de `Logo Dilda Novo.png`). Evite espaços e caracteres especiais em nomes de arquivos web.

---

## 2. Configurando o Git e o `.gitignore`

O arquivo `.gitignore` já foi criado na raiz do seu projeto. Ele instrui o Git a ignorar arquivos que não devem ser enviados para a web, como arquivos temporários do sistema operacional (`.DS_Store`) e planilhas ou PDFs com dados sensíveis do negócio.

### Comandos Iniciais para Publicar no GitHub via Terminal:

Caso deseje enviar este diretório para o GitHub manualmente pelo terminal da sua máquina, siga este fluxo:

1. **Inicializar o repositório local**:
   ```bash
   git init
   ```

2. **Adicionar os arquivos organizados**:
   ```bash
   git add .
   ```

3. **Criar o primeiro Commit**:
   ```bash
   git commit -m "feat: estrutura inicial do portal de boas-vindas"
   ```

4. **Vincular ao seu repositório remoto no GitHub**:
   ```bash
   git remote add origin https://github.com/SEU_USUARIO/NOME_DO_REPOSITORIO.git
   ```

5. **Definir a branch principal como main**:
   ```bash
   git branch -M main
   ```

6. **Enviar os arquivos**:
   ```bash
   git push -u origin main
   ```

---

## 3. Publicando com o GitHub Pages

O GitHub Pages é uma ferramenta gratuita e excelente para hospedar sites estáticos (HTML, CSS e JavaScript).

### Passo a Passo para Ativação:
1. Vá até o seu repositório no [GitHub](https://github.com).
2. Clique na aba **Settings** (Configurações) no topo direito.
3. No menu lateral esquerdo, sob a seção *Code and automation*, clique em **Pages**.
4. Sob a opção **Build and deployment**:
   - **Source**: Selecione *Deploy from a branch*.
   - **Branch**: Selecione `main` (ou a branch principal que enviou) e a pasta `/ (root)`.
5. Clique em **Save**.
6. Aguarde de 1 a 2 minutos. O GitHub gerará um link público no topo da página (ex: `https://seu-usuario.github.io/nome-do-repositorio/`).

---

## 4. Melhores Práticas de Controle de Versão

- **Commits Pequenos e Frequentes**: Evite fazer commits gigantes com dezenas de alterações diferentes. Prefira commits focados em uma única melhoria (ex: `fix: corrige cor do botão do card de sinistros`).
- **Segurança de Dados**: Nunca commite arquivos `.env`, chaves de API, senhas ou planilhas com dados reais de clientes (como a `Projeto 360.xlsx` ou relatórios de vendas). O arquivo `.gitignore` já bloqueia arquivos `.xlsx`, `.xls` e `.pdf` para sua segurança.
- **Uso de Custom Domains**: Se for utilizar um domínio próprio (ex: `boasvindas.dildaseguros.com`), insira-o no campo *Custom domain* dentro das configurações do GitHub Pages e adicione a entrada CNAME correspondente no seu provedor de DNS (como a Cloudflare ou Registro.br).
