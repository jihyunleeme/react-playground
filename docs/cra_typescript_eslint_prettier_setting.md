# CRA + Typescript + ESlint + prettier 설정하기

## 프로젝트 생성 및 이동

yarn npx 둘 중 하나 선택하여 프로젝트를 생성한다.  
`--template typescript` : 자바스크립트 대신 타입스크립트 사용하여 생성

```bash
# yarn으로 설치
$ yarn create react-app react-typescript-boilerplate --template typescript

# npx로 설치
$ npx create-react-app react-typescript-boilerplate --template typescript
```

생성된 프로젝트로 이동

```bash
$ cd react-typescript-boilerplate
```

## eslint & prettier

CRA에는 ESlint 포함되어있어 설치할 필요 없음.

```bash
$ yarn add eslint-plugin-prettier eslint-plugin-react prettier -D
```

root directory에 `.eslintrc`파일 생성하고 다음 내용 붙여넣기

```json
{
  "extends": ["plugin:prettier/recommended"],
  "plugins": ["react", "prettier"],
  "parserOptions": {
    "ecmaVersion": 6,
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "rules": {
    "prettier/prettier": ["error", { "singleQuote": true }],
    "react/jsx-uses-vars": "error"
  },
  "ignorePatterns": ["*.config.js"]
}
```

root directory에 `.prettier` 파일 생성

```json
{
  "singleQuote": true,
  "semi": true,
  "useTabs": false,
  "tabWidth": 2,
  "trailingComma": "all",
  "printWidth": 80
}
```
