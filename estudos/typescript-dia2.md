# Estudos de TypeScript: 20 a 22/nov

## 1. Variáveis (gavetas)
- `let`: guarda um valor que pode mudar.
- `const`: guarda um valor fixo, que não muda.
- Pergunta para escolher: depois de guardado, esse valor muda durante o jogo?

```ts
const duracaoDoAlho: number = 2;
let quantAlho: number = 6;
```

## 2. Os três tipos
- `number`: números, sem aspas.
- `string`: texto, entre aspas.
- `boolean`: só `true` ou `false`.

```ts
let cadernos: number = 3;
let tituloCaderno: string = "Estudos";
let cadernoAberto: boolean = true;
```

## 3. Criar e trocar
- Criar a gaveta: acontece uma vez, com `let` ou `const`, o nome e o tipo.
- Trocar o conteúdo: só o nome, sem `let` e sem tipo.

```ts
let cadernos: number = 5;   // criar
cadernos = 4;               // trocar
```

## 4. Comentários
- `//` e o computador ignora o resto da linha.

```ts
let noitesQueFaltam: number = 2; // começa com 2 noites
```

## 5. Decisões (`if`)
- `if` faz uma pergunta de sim ou não.
- `else if` é a pergunta seguinte.
- `else` é "em todos os outros casos" e não leva pergunta.
- O computador lê de cima para baixo e para na primeira pergunta verdadeira.

```ts
let cidade: string = "Alagoas";

if (cidade !== "Recife") {
  console.log("a cidade é diferente");
} else {
  console.log("são cidades iguais");
}
```

## 6. Símbolos de comparação
| Símbolo | Pergunta |
|---|---|
| `===` | é igual a? |
| `!==` | é diferente de? |
| `<` | é menor que? |
| `>` | é maior que? |
| `<=` | é menor ou igual a? |
| `>=` | é maior ou igual a? |

- `=` guarda um valor. `===` pergunta se é igual.

## 7. `console.log`
- Escreve no console (aba Logs do Playground ou F12 no navegador).
- Não aparece na tela do jogo, serve só para testar.

## 8. Funções
- É uma receita com nome: ingredientes (parâmetros), modo de preparo e resultado.
- Escrever a função só guarda a receita. Ela roda quando é chamada: `nomeDaFuncao();`
- `return` devolve um resultado. `void` significa que não devolve nada.

```ts
function totalDeCompra(precoUnitario: number, quantidade: number): number {
  return precoUnitario * quantidade;
}
```

## 9. Minha função do alho
```ts
let corAlho: string = "Arroxeado";
let noitesQueFaltam: number = 2;

function passarNoite(): void {
  if (noitesQueFaltam > 0) {
    noitesQueFaltam = noitesQueFaltam - 1;

    if (noitesQueFaltam === 2) {
      corAlho = "Arroxeado";
      console.log(corAlho);
    } else if (noitesQueFaltam === 1) {
      corAlho = "Amarelado";
      console.log(corAlho);
    } else if (noitesQueFaltam === 0) {
      corAlho = "Marrom";
      console.log(corAlho);
    }
  }
}

passarNoite();
```
- O `if` de fora protege a conta: com 0, nada acontece e o número nunca fica negativo.
- Dentro dele, a conta vem antes da pergunta das cores.
- 1ª chamada: Amarelado. 2ª: Marrom. 3ª: nada.

## 10. Repetição (`while`)
- Repete enquanto a pergunta der sim, como o `while` do Python.
- Não serve para `passarNoite`: ela passa uma noite por vez, com tempo entre elas.
- `break` sai de uma repetição. Não é necessário no `if`.

## 11. Pendências
- Aprender repetições, listas e classes no estudo do Excalibur.
- Padronizar maiúsculas e minúsculas nos textos das cores.
- Criar a função de trocar o alho (volta para 2 noites e arroxeado).
- Criar uma gaveta para o alho da horta.