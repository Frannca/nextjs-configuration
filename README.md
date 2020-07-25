# Configuração

## 1. Instalar o next

`yarn create next-app`

## 2. Deletar a pasta api

`pages/api`

## 3. Configurar o typescript

1. `touch tsconfig.json`
2. `yarn dev`
3. `yarn add --dev typescript @types/react @types/node`
4. `yarn dev`

## 4. Alterar tsconfig.json

Mudar `"strict": false` para `"strict": true`

## 5. Criar pasta src

1. Criar pasta `src`na raiz do projeto
2. Mover pasta `pages` para dentro da pasta `src`

## 6. Renomear index.js

Alterar nome do `src/index.js` para `src/index.tsx`

Obs.: usar `tsx` para arquivos com HTML e `ts` para arquivos sem HTML

## 7. Criar arquivo .editorconfig

1. Criar arquivo `.editorconfig` na raiz do projeto
2. Atualizar arquivo com o código abaixo:

```
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
```

## 8. Instalar eslint

1. `npx eslint --init` com as configurações abaixo:

```
How would you like to use ESLint? · problems
✔ What type of modules does your project use? · esm
✔ Which framework does your project use? · react
✔ Does your project use TypeScript? · Yes
✔ Where does your code run? · browser
✔ What format do you want your config file to be in? · JSON
✔ Would you like to install them now with npm? · No
```

2. `yarn add --dev eslint-plugin-react@latest @typescript-eslint/eslint-plugin@latest @typescript-eslint/parser@latest eslint@latest`

## 9. Instalar eslint-plugin-react-hooks

1. `yarn add eslint-plugin-react-hooks --dev`
2. Adicionar `"react-hooks"` dentro de `.eslintrc.json` > `"plugins"`
3. Adicionar o código abaixo dentro de `.eslintrc.json` > `"rules"`

```
"react-hooks/rules-of-hooks": "error",
"react-hooks/exhaustive-deps": "warn"
```

## 10. Desabilitar o react/prop-types

Adicionar `"react/prop-types": "off"` dentro de `.eslintrc.json` > `"rules"`

## 11. Desabilitar o react-in-jsx-scope

Adicionar `"react/react-in-jsx-scope": "off"` dentro de `.eslintrc.json` > `"rules"`

## 12. Desabilitar o react-in-jsx-scope

Adicionar `"@typescript-eslint/explicit-module-boundary-types": "off"` dentro de `.eslintrc.json` > `"rules"`

## 13. Informar versão do React

Adicionar o código abaixo em `.eslintrc`:

```
"settings": {
  "react": {
    "version": "detect"
  }
},
```

## 14. Adicionar eslint src dentro do package.json

Adicionar no `package.json` dentro de `"scripts"` o código `"lint": "eslint src"`

## 15. Instalar o lint

`yarn add eslint-config-prettier --dev`

## 16. Criar arquivo .prettierrc

1. Criar o arquivo `.prettierrc`
2. Adicionar o código abaixo:

```
{
  "trailingComma": "none",
  "semi": false,
  "singleQuote": true
}
```

## 17. Instalar prettier

`yarn add prettier eslint-config-prettier eslint-plugin-prettier --dev`

## 18. Integrar prettier com o lint

Adicionar o código `"plugin:prettier/recommended"` dentro do arquivo `.eslintrc.json` > `"extends"`

## 19. Criar configurações do VS Code

1. Criar a pasta `.vscode`
2. Criar o arquivo `settings.json` dentro da pasta `.vscode`
3. Adicionar o código abaixo dentro do `settings.json`:
```
{
  "window.zoomLevel": 1,
  "editor.fontSize": 12,
  "terminal.integrated.fontSize": 12,
  "editor.formatOnSave": false,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  }
}
```

## 20. Instalar o husky

`yarn add --dev lint-staged husky`

## 21. Atualizar lint para forçar que os warnings também sejam erros

No `package.json` alterar `"lint": "eslint src"` para `"lint": "eslint src --max-warnings=0"`

## 22. Configurar o husky

Adicionar o código abaixo dentro do `package.json`:

```
"husky": {
  "hooks": {
    "pre-commit": "lint-staged"
  }
},
```

## 23.

Adicionar o código abaixo dentro do `package.json`:

```
"lint-staged": {
  "src/**/*": ["yarn lint --fix"]
},
```
