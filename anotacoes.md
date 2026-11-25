# Anotações do projeto Eu Sou a Lenda

## 17/nov: o que fiz

- Instalei o Node.js e criei o repositório público no GitHub.
- Pensei nas ações do jogador de dia e de noite, a partir do livro.
- Transformei o alho em mecânica.
- Escrevi as 4 primeiras tarefas de desenvolvimento.

## 18/nov: o que fiz

- Criei o cronograma no GitHub Projects (Roadmap), com 19 tarefas de 17/nov a 07/dez.
- Decidi escrever o README aos poucos (26/nov a 06/dez) e deixar o dia 07/dez livre como margem de segurança.
- Dividi o estudo do Excalibur.js em duas partes e marquei a criação do projeto base para o dia 22/nov.
- Decidi aplicar os sprites junto de cada tarefa e anotar links e licenças dos assets no dia 26/nov.
- Defini o mapa em 3 zonas (casa, horta, rua) em uma tela fixa, usando Darkwood apenas como inspiração.
- Cortei por enquanto: câmera e mapa grande, animação do personagem andando, stamina, ruínas e estacas.
- Defini a ordem de corte dos dias 04 e 05/dez: inimigos, alho, game over, menu e polimento.
- Deixei o projeto público no GitHub.

## 19/nov: o que fiz

- Rodei `git status` na pasta do repositório clonado (ramo main, tudo limpo).
- Criei este arquivo (`anotacoes.md`) para o primeiro commit.

## As 4 primeiras tarefas (o que aparece na tela)

1. **Tela do jogo:** fundo preto com o texto "teste" no canto.
2. **Cenário:** chão cinza e casa marrom-escuro.
3. **Personagem parado:** quadrado amarelo no meio da casa.
4. **Movimentação:** W, A, S, D movem o quadrado para cima, esquerda, baixo e direita.

## Mecânica do alho

- Dura 2 noites.
- Muda de cor em 3 etapas: arroxeado, amarelado e marrom (marrom = sem efeito).
- É colhido na horta, fora de casa, durante o dia.
- Se o alho acabar, os vampiros conseguem entrar na casa.

## Mapa

- Tela fixa, dividida em 3 zonas: casa no centro (paredes sólidas e uma porta), horta ao lado e rua cinza ao redor.
- Os inimigos aparecem pelas bordas da rua à noite.
- Darkwood é apenas inspiração de clima e estrutura.

## Ideias para depois (só se sobrar tempo)

- Dias nublados aleatórios, em que o perigo aparece também de dia.
- Relógio na tela ou apenas o alho envelhecendo para mostrar o tempo.
- Câmera e mapa grande.
- Animação do personagem andando.
- Estacas e ruínas na rua (carros e entulho).

## Cortado por enquanto

- Stamina e botão de correr.
- Estacas em volta da casa.

## 20 e 22/nov: o que aprendi

### Decisões (`if`)
- `if` faz uma pergunta de sim ou não. `else if` é a pergunta seguinte. `else` é "em todos os outros casos" e não leva pergunta.
- `=` guarda um valor e `===` pergunta se é igual.
- O computador lê de cima para baixo e para na primeira pergunta verdadeira.

### Funções
- Função é uma receita com nome: ingredientes (parâmetros), modo de preparo e resultado.
- `void` significa que a função não devolve nada, só faz um trabalho.
- Escrever a função só guarda a receita. Ela só roda quando é chamada: `passarNoite();`

### Minha função do alho
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
         } else if(noitesQueFaltam == 0) {
            corAlho = "Marrom";
             console.log(corAlho);
        }

    }   
}

passarNoite();
```


## 23/nov: o que estudei

- **Engine, Scene e Actor:** A `Engine` é o motor que controla e roda o jogo inteiro; a `Scene` é cada tela ou fase (menu, fase 1, game over); e o `Actor` é qualquer elemento que aparece e interage na tela (jogador, inimigos, itens).
- **Coordenadas x e y:** O ponto `(0, 0)` fica no canto superior esquerdo da tela. O eixo `x` aumenta para a direita e o eixo `y` cresce para baixo.
- **Loop do jogo:** É um ciclo contínuo (`update` + `draw`) que roda dezenas de vezes por segundo para ler comandos, atualizar posições e redesenhar a tela.
- **Cálculo de velocidade:** É definido multiplicando os passos (pixels) por atualização pela quantidade de atualizações por segundo (FPS), garantindo movimento constante usando o tempo entre frames (`delta`).


## 24/nov: o que fiz

- **Pasta do projeto:** Criei a pasta `eu-sou-a-lenda` dentro do repositório principal para manter todo o histórico de estudos, anotações e o código do jogo organizados em um único lugar.
- **Configuração com a CLI:** Rodei o criador oficial escolhendo as opções **Create a game**, **TypeScript with Vite** e confirmei a **instalação das dependências** automaticamente.
- **Execução local:** Subi o servidor de desenvolvimento e validei o funcionamento do projeto base abrindo o jogo no navegador em `localhost:5173`.
- **Estrutura vs. Autoria:** Entendi que a estrutura inicial (arquivos base e configurações) foi gerada pela ferramenta oficial do Excalibur, mas toda a lógica, mecânicas e código do jogo serão desenvolvidos por mim.
- **Projeto base no ar:** Criei a pasta `eu-sou-a-lenda` dentro do repositório usando `create-excalibur` (TypeScript + Vite), validei em `localhost:5173` e entendi como os scripts do `package.json` (`start`) e o `.gitignore` funcionam.
- **Classes e objetos (molde de biscoito):** A classe é o molde que define o tipo da coisa e suas características (gavetas), enquanto cada objeto criado a partir dela é um item individual com seus próprios valores (ex: 1 molde `Alho` para criar 5 alhos diferentes pendurados).


## Decisões de design
- O relógio do jogo decide quando o dia acaba (Timer, 4 a 5 minutos). A função `passarNoite` só faz a conta quando é chamada.
- Tela cinza-escura para dar clima sombrio. Decidir as cores na tarefa do cenário (#11).
- `console.log` não aparece na tela do jogo, serve só para testar. Quem mostra a cor do alho é o sprite.
- A horta precisa de uma gaveta própria, além de `quantAlho` (alho na mão).

## Pendências
- Padronizar maiúsculas e minúsculas nos textos das cores.
- Decidir o que o `else` faz se `noitesQueFaltam` tiver um valor que não existe, como 5 ou -1.
- Repetições, listas e classes: ver no estudo do Excalibur.

## Site do Jogo
- [text](https://mirandaline432-max.github.io/Atividade-Final-EU-SOU-A-LENDA/)