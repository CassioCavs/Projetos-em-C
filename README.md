Código criado Pelo Cássio Lima, Andrey Ranieri e Arthur Eutrópio.
Atividade feita para o CESUPA na disciplina de programação 1 e solicitada pelo professor Pedro Girotto.

Essa atividade tem como objetivo criar um Role-Playing Game, também conhecido como RPG, é um tipo de jogo em que 
os jogadores assumem papéis de personagens e criam narrativas
colaborativamente. O progresso de um jogo se dá de acordo com um sistema de
regras predeterminado, dentro das quais os jogadores podem improvisar
livremente.

O objetivo do projeto é desenvolver um sistema de combate em turno que será
aplicado em um jogo de JRPG.
Ao iniciar o aplicativo, o jogador se depara com um menu inicial. Contendo a
opção de começar o jogo, contar a história que envolve o jogo e fechar jogo.
Ao escolher a opção história, deve ser mostrado um texto contando uma breve
história do seu mundo de fantasia e o principal motivo do personagem querer
enfrentar o desafio.
A opção começar jogo inicializa o jogo, que segue o fluxograma da Figura 1. O
jogador criará seu personagem que tentará vencer três combates, onde a cada
vitória de um combate dará uma recompensa para o jogador. O jogo vai se
tornando mais difícil à medida que vencemos os combates.
Se as três lutas forem vencidas, chegaremos em uma tela de vitória, e se
perdemos um combate, uma tela de derrota é mostrada e voltaremos para o início
do jogo.

O personagem do jogo contém as seguintes características:
• Status Básicos:
o Nome;
o P.V. (Ponto de Vida);
• Atributos:
o Força;
o Constituição;
o Agilidade;
o Destreza;
• Equipamentos:
o Arma;
o Armadura.

A força influencia no dado da arma pesada. Constituição influencia na
quantidade de P.V. e na defesa. Agilidade influencia na ordem dos turnos durante o
combate. Destreza influencia no dano da arma leve.
As armas possuem as seguintes características:
• Arma:
o Categoria;
o Dano.

A categoria de uma arma pode ser dois: pesada e leve, na qual influência no
valor do dano.
O dano de uma arma pesada é calculada pela soma da rolagem de um dado
de 12 lados (d12) mais 1,5 do valor da força e mais um valor constante.
O dano de uma arma leve é calculada pela soma da rolagem de dois dados de
6 lados (d6) mais a rolagem de um dado de 4 lados (d4) mais o valor da destreza
mais o valor de uma constante.
As armaduras possuem as seguintes características:
• Armadura:
o Defesa.

A defesa da armadura é calculada a partir de um número constante mais 1,5
do valor da constituição.
O ponto de vida é calculado pela soma da rolagem de três dados de 6 lados
(d6) mais o valor da constituição.
Resumindo as características temos:
• Status Básicos:

o P.V. = d6 + d6 + d6 + Cons.;
• Equipamentos:
o Arma Pesada = K + d12 + 1,5*For.;
o Arma Leve = K + d6 + d6 + d4 + Des.;
o Armadura = K + 1,5*Cons.;

Ao começar a criação do personagem (Figura 2), o jogador deve dar um nome
ao personagem, distribuir 15 pontos nos atributos e escolher uma armar e armadura.
Onde o usuário poderá escolher uma das 3 armas iniciais e uma das 3 armaduras
iniciais.

No combate, o personagem lutará contra um adversário, que contêm as
seguintes características:
• Adversário:
o Nome;
o P.V. (Ponto de Vida);
o Dano;
o Defesa;

o Agilidade.

O P.V. do adversário, defesa e agilidade são valores constantes decido pelo
programador. O dano do adversário poder ser um valor constante ou um valor
aleatório, essa decisão e esses valores fica a critério do desenvolvedor.
O combate envolve a sequência apresentada na Figura 3. Ao iniciar o combate,
deve ser verificado quem é mais rápido (maior valor na agilidade), caso seja o jogador,
ele terá o primeiro round, se não o primeiro round vai para o adversário. Após ambos
fazerem suas jogadas, verificamos se alguém morreu (P.V. igual ou menor que zero),
se o jogador morreu, o jogo termina e voltamos para o menu principal; se o adversário
morreu, o jogador ganha sua recompensa e passamos para a próxima luta; se
ninguém morreu, o jogador e o adversário jogam mais um round, e isso se repete até
alguém morrer. O adversário deverá ser escolhido de forma aleatória para cada combate,
fazendo o jogo ser aproveitado mais de uma vez.

No turno do jogador terão três ações disponíveis:
• Ações:
o Atacar;
o Defender;
o Usar Poção.

A ação atacar faz o personagem causar dano ao adversário. O dano causado
no adversário é calculado pegando o valor do dano da armada do jogador menos a
armadura do adversário. Com o valor do dano calculado, subtrai-se do P.V. do
adversário.
Defender dobra o valor da defesa do personagem por 1 round.
Usar Poção recupera os P.V. do jogador, esse valor é calculando fazendo a
soma da rolagem de três dados de 6 lados. O jogador só tem acesso a três poções
por combate.

Mesma ideia do jogador, porém quem escolhe a ação é o computador. Um
número aleatório entre 0 e 2 é gerado e a partir desse valor uma ação é selecionado.

• Ações:
o 0 - Atacar;
o 1 - Defender;
o 2 - Usar Poção.

Ao vencer cada combate, o jogador receberá uma premiação.
• Primeira Premiação:
o Subir um level;
o Mais P.V.;
o Opção de escolher uma nova armar de 3 opções disponíveis.
Ao subir um level, o jogador ganhar mais 5 pontos de atributos para serem
distribuídos.
O novo valor do P.V. é feito pegando o antigo valor máximo de P.V. e
acrescenta o valor da constituição.
O usuário poderá escolher uma das 3 armas apresentadas, essas novas armas
devem ser mais fortes do que as armas iniciais.

• Segunda Premiação:
o Subir dois leveis;
o Mais P.V.
o Opção de escolher uma nova armadura de 3 opções disponíveis.
Ao subir dois leveis, o jogador ganhar mais 10 pontos de atributos para serem
distribuídos.
O novo valor do P.V. é feito pegando o antigo valor máximo de P.V. e
acrescenta o valor da constituição.
O usuário poderá escolher uma das 3 armaduras apresentadas, essas novas
armaduras devem ser mais fortes do que as armaduras iniciais.

• Terceira Premiação:
o Fim do jogo.

Na terceira premiação o jogador venceu o jogo, então uma tela de vitória é
mostrada e a conclusão da história.
