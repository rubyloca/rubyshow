BOA DANÇA ~
Um pouco da minha experiencia na area de bugs otserv.
reportado em detalhes.

Retired Tibia - 4ver - 

--------------------------------------------------------------
---------------------------------------------------------------
1 - Bug do Sample: Envie dinheiro por transfer para quaisquer character Sample do servidor, exemplo: Knight Sample, Sorcerer Sample, etc.. E então todos os characters novos que criarem conta vão vir com o dinheiro que você transferiu para o Sample.

---------------------------------------------------------------
---------------------------------------------------------------

2 - Bug House: Entupa a casa de lixo, leather boots, ou items não estaquiaveis, e então de !leavehouse.

existem 2 formas de fazer esse bug, com varios itens em stack na house
ou varios itens dentro de varias bps, estocados, dentro de uma bp na house.

assim que os itens forem enviados para o Mail, o servar Laga. "cai"

não causa rollback, porém, pode ser que se tiver Muito item mesmo dentro de muitas bps, tudo estocado, pode ser que de um error da distro quando der !leavehouse ou save no server, podendo causar rollback.
(* o do rollback não testei).

----------------------------------------------------------------
----------------------------------------------------------------

3 - Bug Stack SAVE/CLEAN: O bug é baseado em colocar muitos itens na stack.
existem varios modos de faze-lo, o mais simples, achar um npc dar ignore capacity e ir compando de 100 em 100 algum item barato, por exemplo: shovel, pick, rope...

apartir de 500 paginas do brownser field, já começa lagar, quando tiver 800 
900 paginas começa a travar o OT, e na hora so server save o server junto com o site cai, por uns 2 ~~ 8 minutos,(varia). OT "cai" sem rollback, pois a distro não fecha.

(Se fizer com muitos itens estocados na BP na hora do save, pode também dar erro na distro, podendo causar rollback)


----------------------------------------------------------------
----------------------------------------------------------------


4 - Bug de Crash: Coloque vários items na stack, e do lado da stack, utilize browse field, o servidor vai carregar..
(me passaram esse bug, testei e não obtive resultado).

----------------------------------------------------------------
----------------------------------------------------------------

uma leve explicação de um admin de otserv, apelidado de Vank:

Simplificando, quaisquer bugs que tenha muito items em um SQM ou stack, pode fazer o servidor crashar, isso é um problema no protocolgame.cpp, poucos servidores tem isso arrumado.

----------------------------------------------------------------
----------------------------------------------------------------

5 - BUG HotkeyEquipe das distro 10.0+ 1.1 /1.2 possuí um BUG.
todos que conhecem um bug do stealth ring, acredita que seja isso o causador, mas estudando esse bug eu descobri que não tem nada a ver com o stealth ring, o BUG é no HotkeyEquip.

Esse bug existe muitas variações, pode ser feito por exemplo, segurando o "F9"(não precisa ser necessariamente o F9) com autoequipe em algum item
provavelmente o Server crash com Rollback.

Se utilizar com wpe, ou rPE, as chancer de cairem são certas, caso a Distro tenha erro nisso.

Não é possível conserta-lo colocando delay, acompanhei alguns ADMS com seus servers, e descobri que o delay ajuda a prevenir, porem ainda há possibilidades de ser derrubado.

- Farei um breve relato, um server coloco um delay bem grande na HotkeyEquipe e eu descobri uma forma de derrubar com o rPE, segue oque eu fiz :

consegui derrubar o baiak-aurea do vank
da seguinte forma.
ele diminuiu o delay do autoEquip. certo

~ item usado, Hat inicial de mage, (aquele de armor 1 ou 3 se não me engano).
programa utilizado - Redox packet Editor.

equipa na mao /\  - packet 30 (RPE - REDOX PACKET EDITOR)
equipa hotkey     - packet 30 (RPE - REDOX PACKET EDITOR)
equipa na mão \/  - packet 30 (RPE - REDOX PACKET EDITOR)
chapeu tem que começar estando na backpack.
essa é a ordem

*start no programa.
equipa o hat mão /\      (puxando o item mouse)
desequipa na  mão \/     (puxando o item mouse)
equipa hotkey /\       (exemplo F9)
*Stop no programa.

puxa com a mão o hat para backpack \/

coloca velocidade packet em 30, e da start no programa.
OT crash em 5 ~ 25 segundos.

claro que pode existir variaçoes e tal, o bug continua sendo do HotkeyEquip.

Eu desconfio que o bug tenha haver com o programa puxar o hat para o set e ao mesmo tempo o hotkeyEquipe faz isso, oque causa Debug, se não ocorrer Debug, o ot crash. 

Esse bug é critico e abre possíbilidades a muitos outros que podem ser no momento desconhecidos.

--------------------------------------------------------------
--------------------------------------------------------------

6 - -Bug "FALSO CLONE", e itens agrupaveis, (testei com flechas)

Exemplo:

compra 101 flechas, Deixa as 100 equipadas -

*Start no Programa (rPE)
puxa para backpack 51 \/
puxa devolta para o lugar dela as 51 /\
E usa o hotkeyEquipe na flecha.
*Stop o programa.


coloca o packet por volta do 30 ~ 40 e start
as flechas começam a ser "clonadas" em falso. só na interface do tibia.
e vai lotando a backpack disso, chega uma hora e da debug, se não desse o debug, acredito que o OT crasharia. ~~~~~

-------------------------------------------

 - Juntamente O "BUG do Crossbow ou itens de 2 mão"

Tem que ter 2 fator pra clonar...
1° poder colocar items agrupaveis na mão
2° subir a crossbow na mão e tirar o shield

se tiver esses 2 fator vc deixa 100 items agrupaveis na mão, por Exemplo, 100 Gold, 100 Food, 100 Worn. etc...
E Deixa 1 na backpack.

Exemplo 100 gold na mão, e um 1 Gold na backpack


Deixa uma crossbow ou qualquer outro item de 2 mão na backpack
encha a backpack com itens.
Exemplo, preencha todo o espaço que ficou vazio com Label na backpack.

Então empura a crossbow para a mão aonde está os 100 gold
nisso o primeiro item agrupavel que estiver na backack vai se tornar 100.

ai vai clonar o item.

(esse bug, foi passado para mim a pouco tempo, já não tenho interesse por Tibia por isso nem testar eu testei.)

---------------------------------------------------------------
---------------------------------------------------------------


7 - Um BUG RARO, o Inbox do Depot é limitado a uma quantia X de itens, passando dessa quantia não tem como colocar mais itens dentro da Inbox, justamente para evitar Bugs.
Porém existe uma forma de burlar esse sistema.

Utilizer o rPE e descobri uma falha nisso, fiz o seguinte:

programei o rPE para fazer o seguinte ciclo, rapidamente.
Comprar backpack
Jogar essa backpack dentro de outra backpack e abri-la.
Depois repitir o processo.
e isso 100 % afk em pouco tempo, as bps criam grande profundidade.

e quando você joga isso no depot, e ele aceita, sempre que você ir la nas ultimas backpack, porque fica uma dentro da outra. você poderá colocar a quantidade de itens e bps que quiser, criando um ciclo infinito, que certamente uma hora dará algum problema no server save, de lag, ou até mesmo de crash.


tecnicamente impossível fazer isso, porem se souber usar rPE, wpe ou  editores de pacotes, fica muito muito rapido mesmo, 10 ~ 20 minutos, 100 %¨afk.

então se o Limite de itens no inbox é 3 mil itens, da para colocar infinitos itens, se for colocado nas bps profundas.

esse processo tem que ser feito organizado, comprando 1 bp de cada vez pelo npc, jogando dentro da outra e abrindo ela.
tudo com programas.

*acredito que não haverão loucos para fazer com a mão hahaha
----------------------------------------------------------
explicação ADM Marlon:

(ou seja muitos itens "food" ham" dentro de bps e bps
tendo muita cap e quantidade, se enviado ao inbox e ficar lá já dara peso no mysql, database, causando assim lag no servidor.

---------------------------------------------------------------
---------------------------------------------------------------

8 - BUG "PARCEL, MARKET" (MAIL).

O bug consiste em lotar o Mail de itens, com varias e varias paginas.
o bug também funciona, caso tenha muitos itens dentro da Backpack que for enviada. 
(não precisa necessariamente lotar varias paginas, pode ser quantidade de itens na backpack).

Bug simples, enviar grande quantidade de itens dentros de bps.. por PARCEL.
*tem que ser grande quantidade mesmo =)

*server laga e cai, não precisa ser itens pesados o bug é a quantidade de itens e não a CAP/PESO.



@ ~~ o Market funciona da mesma forma, porém o processo é outro.
eu por exemplo anunciei 2000 mil colares a preço de 1 gp e cancelei a venda, dai os itens volta para o Mail, e vai repetindo o processo, até Lotar. 

*Pode ser feito com qualquer item, desde que tenha em grande quantidade.


E se o OT não tiver programado para deletar altas quantidades de itens no Mail e os intens ficar lá, toda vez que o player logar e deslogar o CHAR o Server Vai TRAVAR Hard.

e pode ser que se o char ficar ligado, forçará a maquina em que o server ta hospedado, podendo causar Lags.

-----------------------------------------------------------
-----------------------------------------------------------

9 - Bug inutil, 

programar no rPE para salvando o outfuit atual e o comando !changesex
faz o CHAR andar "mancando" é engraçado até.


-----------------------------------------------------------
-----------------------------------------------------------

10 - Bug House Rollback  (*bug não confirmado).

Lotar a house de lixo, paginas e paginas nas stack, e deixar os itens lá
e não pagar o aluguel e nem logar o char (dependendo do sistema que o ot usa), quando o char for expulso da house, vai dar um erro na distro, vai rolar rollback, e os itens não vão para o Mail, vão continuar na House.

----------------------------------------------------------
----------------------------------------------------------

11 - BUG BAÚ QUEST, com mc e mw coloque um char em cima de um baú de quest
tem que ter 2 bau um do lado do outro.
então suba em cima de um logando o char e tacando mw em volta, quando logar, estará em cima do Baú, e mova seu char para o Baú ao lado, isso criará um Loop infinito crashando o OT com rollback.

serve não somente para Baús, mas para pisos com Action de movimento.
EXEMPLO:

https://www.youtube.com/watch?v=ube4b-q4Ncg

com mcs também você pode acessar algumas areas VIP do server, se as mesmas não tiver proteção.

-----------------------------------------------------------
-----------------------------------------------------------

12 - BUG EXPLOIT (cast), configura rPE ou wpe, para ir de uma cidade a outra muito rapidamente, e usa um programa de BOT para ir logando spectadors no CAST SYSTEM, isso causa Lag, e todos serão desconectador do OT LAGS/KICKS. acredito que não de rollback.
no video ele logou + de 600 spectadors no Cast.

nunca testei, porém existe um video do AVZ no youtube mostrando, Saudações ao Avz e seus bugs loucos. kkkk

https://www.youtube.com/watch?v=CJ6loeCbtvI

-----------------------------------------------------------
-----------------------------------------------------------

13 - BUG DA PORTA, encontrar uma porta (se tiver), que empurre itens, para baixo, quando fechada, então é só lotar a stack de lixo, e fechar a porta, e quando ela empurrar os itens, o server Laga.


-----------------------------------------------------------
-----------------------------------------------------------

14 - Bug Canledando,  (*não testado)

colocar muitos itens para vender e ficar cancelando, dizem que dá Lag.
não cheguei a testar.

-----------------------------------------------------------
-----------------------------------------------------------

15 - FAMOSO BUG DO CAST SYSTEM - 

dizem que ficar spamando magias dentro dele com mcs, e programas, Laga.
*não testado


@ - ROLLBACK cast.
Existe um bug, colocado propositalmente, pelos safadinhos de plantão que compartilham cast nos Foruns.

eu não sei fazer o bug, mas desconfio do que possa ser.

algo relacionado a um simbolo.

 --- EXEMPLOS:


----------------------------------------------------------------
 (((((((((๑۩۞۩๑ ☜ ☞ ☎ ☏♂ ♀♬ ♪ ♩ ♭ ♪o(‧'''‧)o☜♥☞♠ ♣☺ ☻⊕ ¤ ☼ ＃㊚㊛๑۩۩.. ..۩۩๑
╗╬ ═ ╓ ╩ ┠ ┨┯ ┷┓┗ ┛┳⊥﹃﹄┌ ┐└ ┘∟「」
↑↓→←↘↙┇┅ ﹉﹊﹍﹎
㊀㊁㊂㊃㊄㊅㊆㊇㊈㊉㊊㊋㊌㊍㊎㊏㊐๑•ิ.•ั๑))))))

----------------------------------------------------------------

Não sao esses simbo-los e eu desconheço qual seja. também não me dei ao trabalho de procura-lo.

- * as formas que eu suspeito que podem ocorrer o bug.

* Simbo-lo desconhecido * aberto como senha -        EX: !Cast on ♥
* Simbo-lo desconhecido * usado para fechar o cast - EX: !Cast off ♥
* Simbo-lo desconhecido * Usado no defalt do cast EX: ♥ no defalt.

------------------------------------------------------------
------------------------------------------------------------

16 - BUG RUNAS

em alguns OT, jogar runas na aguá pode crashar também.
exemplo: "tacar" a avalanche rune na aguá, no espaço preto, na larva, na gosma verda. etc...

------------------------------------------------------------
------------------------------------------------------------

17 - BUG ANIMATE RUNE

Se no servidor os bixos sumonados, dão teletransporte até quem os criou
pode existir um bug que é com Animate rune, você Monta uma trap em algum buraco com itens em volta que não permitir que suba em cima, e nem que os bixos empurrem, use a runa, Junte Muitos skeletons, uns 40 + e quando pular no buraco, crasha o server.

------------------------------------------------------------
------------------------------------------------------------

18 - BUG DO BANK E REPORT

BANK - Libere toda sua CAP, compre muitas backpacks, tenha muito dinheiro no BANCO, e use o rPE ou wpe, para depositar e retirar o Dinheiro rapidamente, isso causará Lag, praticamente imediato.
tem que ser + de 300kk, por volta dos 400 ~ 800kk
funciona + em servidores de exp alta.


@ - BUG REPORT 
Usar os mesmos programas para ficar pacotando a database do OT, atráves do Ctrl + z, que geralmente é usado para reportar BUGS.

------------------------------------------------------------
------------------------------------------------------------

------------------------------------------------------------

Bugs que eu conheço da versão 8.5, 8.6 


!disband -  tem explicação na internet * creio que já foi fixado a muito tempo

!deathlist - não sei fazer, se alguém souber, favor compartilhar conhecimento...

------------------------------------------------------------
------------------------------------------------------------




Informações  ~~ :
Houses, com NPCS que vendem itens baratos ao lado, é mamata para facilitar os bugs, comprando tudo direto na house.

------------------------------------


existe o bug de ir colocando bp dentro de bp com rPE, wpe como já citei.
até ficar muito pesado. e depois colocar itens dentro.

fazer dentro de houses com NPC ao lado é mais facíl.

outra forma é fazer isso no depot também, causa os mesmo problemas, no depot é recomendado fazer do lado de um npc que vende parcel, e ir colocando um parcel dentro do outro..

------------------------------------

voltaréi a falar do BUG numero 7 -
uma breve citação, é possivel através da profundidade, das bps, colocar não somente itens dentro do depot mesmo quando ultrapassar o limite, mas também funcionar para colocar itens dentro de backpacks profundas dentro do Mail.
(ou seja, coloca itens lá dentro atrávez de parcel ou backpacks que já estão lá dentro)...

------------------------------------




