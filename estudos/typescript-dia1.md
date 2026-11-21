# Estudos de TypeScript - Dia 1

## Variáveis e constantes

- `let`: serve para armazenar valores (`string`, `number` e `boolean`) que podem ter seus valores manipulados depois.
- `const`: serve para armazenar valores fixos (`string`, `number` e `boolean`) que não podem ser alterados.
- Se eu tentar mudar o valor de uma constante depois (como `duracaoDoAlho = 3;`), o TypeScript acusa um erro.
- **O que diferencia as duas:** mesmo aceitando os mesmos tipos de dados, `let` permite trocar o valor guardado ao longo do programa, enquanto `const` trava o valor inicial para não mudar.

## Os três tipos

- `number`: guarda números inteiros ou decimais, escrito sem aspas. Exemplo: `let cadernos: number = 3;`
- `string`: guarda textos, sempre escrito entre aspas. Exemplo: `let tituloCaderno: string = "Estudos";`
- `boolean`: guarda verdadeiro (`true`) ou falso (`false`), escrito sem aspas. Exemplo: `let cadernoAberto: boolean = true;`

## Criar e trocar o valor

- **Criar a gaveta:** escrevo `let` (ou `const`), o nome da variável e o tipo apenas na primeira vez para reservar o espaço. O `const` também cria uma gaveta com esse mesmo formato, mas já vem trancada para não mudar depois. Exemplo: `let cadernos: number = 3;` e `const maxCadernos: number = 10;`
- **Trocar o conteúdo:** depois que a gaveta (`let`) já existe, uso apenas o nome dela para colocar um novo valor, sem escrever `let` nem o tipo novamente. Exemplo: `cadernos = 5;`

## As gavetas do alho no jogo

```typescript
const duracaoDoAlho: number = 2;
let noitesQueFaltam: number = 2;
noitesQueFaltam = 1; // acontece quando a primeira noite passa e falta 1 noite
let quantAlho: number = 6; // vai variar durante a colheita, por isso usa let
let corAlho: string = "arroxeado"; // cor inicial quando colho o alho na horta
corAlho = "amarelado"; // acontece nesse mesmo momento, quando passa a primeira noite e falta 1 noite
corAlho = "marrom"; // acontece quando a segunda noite passa e faltam 0 noites
```

| Noites restantes | Cor do alho | Efeito no jogo |
| :--- | :--- | :--- |
| **2 noites** | Arroxeado | Alho fresco, protege contra os inimigos |
| **1 noite** | Amarelado | Alho envelhecendo, ainda protege |
| **0 noites** | Marrom | Alho estragado, sem efeito de proteção |
