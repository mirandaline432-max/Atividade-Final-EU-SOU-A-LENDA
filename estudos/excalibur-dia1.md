# Estudo Excalibur — Dia 1

## 1. Engine, Scene e Actor
- **Engine:** o teatro onde fica tudo sobre como funciona a tela do jogo e as suas configurações.
- **Scene:** cada "tela" do jogo (menu, jogo, game over). Só uma fica ativa por vez, e é nela que os atores são colocados.
- **Actor:** qualquer coisa que existe no palco e pode ter posição, aparência, movimento e colisão. O `Player` é um Actor, e herda isso dele.

## 2. A cadeia `main.ts` → `level.ts` → `player.ts`
- O `main.ts` inicia a Engine e chama a fase `level.ts`, que adiciona o `player.ts` na tela com `this.add(player)`.

## 3. Classe e objeto
- Classe é o molde (a ficha em branco) que define as características (gavetas) e ações (receitas). Objeto é uma coisa feita a partir dele, com valores próprios (como cada alho com seu `noitesQueFaltam`).

## 4. `extends`
- Significa herança: o `Player` herda o que já existe no `Actor`.

## 5. `this`
- Significa "este mesmo objeto": dentro de uma receita, aponta para o objeto que a está usando.

## 6. O loop
- O flipbook folheia 60 vezes por segundo, e a cada folheada o Excalibur chama `onPreUpdate` e `onPostUpdate`.

## 7. A espada
- A espada é o sprite do `Player` e anda em quadrado: direita, baixo, esquerda, cima.
