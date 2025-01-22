# Simulação de manutenção de aeronaves com Gen Ai
Este projeto é uma tentativa de construir um modelo de simulação do processo de manutenção de aeronaves em uma companhia aréa para ser usado em simulação de vôo.

O projeto é baseado em um prompt do Google Gemini. Este prompt fornece informações sobre as operações da frota de Airbus A340-600 da Lufthansa.
Eu escolhi utilizar esta aeronave para criar este prompt, porque estava simulando algumas operações com A346 da Toliss no Xplane 12 :). 

Também gostaria de entender se era possível construir essa ideia com o Gemini.
Você pode modificar o prompt original para simular as operações de outras companhias aéreas. Um ponto importante é utilizar os prefixos reais e quanto mais informação você adicionar no prompt, melhor vai ser a simulação. 
No meu exemplo, adicionei a idade dessas aeronaves, e utilizei as informações da página  [Plane Spotters](https://www.planespotters.net/airline/Lufthansa) para ter informações sobre a frota de A340-600 da Lufthansa.

O objetivo deste prompt é ensinar o Gemini como acontece as interações entre a manutenção e um piloto. Eu não sou piloto, e nem trabalhei em uma companhia aérea, então não sei se as interações que defini são realistas. Se alguém tem experiência com este tipo de trabalho e quiser contribuir, será muito bem vindo.

Isto tem melhorado bastante minha simulação, principalmente durante o pre-flight. É possível acessar o livro de manutenções e verificar as últimas ocorrências, se tem algum item MEL ativo, etc.
Também é possível ver os últimos vôos daquela aeronave.

## Estrutura do Projeto

O principal arquivo do projeto é um resumo do prompt que eu utilizei para "treinar" o Gemini. Eles se encontra na pasta **prompt-summary**. Para começar a utilizar, copie este prompt e cole no seu chat do Gemini.
Como o Gemini não vai guardar histórico, para continuar utilizando as informações de maneira realista e acessando o histórico das conversas anteriores, você pode fixar um chat e sempre utilizar o mesmo.
Originalmente este prompt foi criado em português, eu gerei uma versão em inglês, mas não sei se ela vai funcionar como esperado.
Dentro da pasta **examples** tem alguns exemplos do uso deste prompt na simulação.

Provalvelmente, depois de colar este prompt no chat, e perguntar algo como: mostre-me o log técnico da aeronave D-AIHC.
Ele deve mostrar apenas uma entrada no log, pois ele não tem muito contexto ainda. Neste caso você pode pedir para ele simular diferentes entradas no log.
Para isso você pode usar um comando como: Você pode simular mais entradas no log técnico da aeronave D-AIHC?
Isso vai fazer que ele adicione mais entradas neste log.

Para ficar mais realista, é interessante ir interagindo com o chat, e dando mais contexto e dados para ele conseguir gerar informações melhores.

Eu testei esse prompt no ChatGPT também, mas os resultados do Gemini me pareceram melhores. De qualquer forma, acho que vale a pena você testar lá e ver se os resultados são melhores para você.

Abaixo segue uma visão geral de como este chat funciona.
Eu espero que isso possa útil e possa adicionar um pouco mais de realismo na sua simulação.

# Simulação de Log Técnico de Aeronaves (Lufthansa A340-600)

Este projeto simula as operações e a manutenção de aeronaves Lufthansa A340-600, mantendo um log técnico realista. O objetivo é criar um ambiente interativo para aprender sobre os procedimentos de manutenção de aeronaves, o uso do MEL (Minimum Equipment List) e a importância da consistência cronológica em registros técnicos.

**Contexto:**

Este projeto utiliza um modelo de linguagem para simular as operações de aeronaves Lufthansa A340-600 (exemplificados pelos registros de D-AIHC, D-AIHI e D-AIHU), mesmo que essas aeronaves já tenham sido aposentadas na realidade. A simulação considera aspectos como:

*   **Cronologia estrita:** Todas as entradas no log técnico seguem uma ordem cronológica precisa.
*   ***Turnaround*:** Tempo em solo entre os voos para desembarque, embarque, reabastecimento e inspeção.
*   **Rotas reais adaptadas:** As rotas simuladas são baseadas em dados históricos de voos reais operados pelos A340-600 da Lufthansa, adaptadas para o presente da simulação.
*   **Ocorrências e Manutenção:** Simulação de ocorrências menores que seriam registradas no log técnico e as respectivas ações de manutenção.
*   **Voos sem ocorrências:** Registro de voos que transcorreram sem problemas.
*   **Separação entre previsão e registro:** Distinção clara entre a previsão de voos futuros (status e próxima rota) e o registro de eventos passados no log técnico.

**Como usar:**

A interação com a simulação é feita através de comandos em linguagem natural. Veja alguns exemplos:

*   **Solicitar o status de uma aeronave:** `Qual o status do D-AIHC?`
*   **Mostrar o log técnico:** `Mostre-me o log do D-AIHU.`
*   **Reportar uma ocorrência:** `Realizei um voo simulado com o D-AIHI, LH123 de FRA para SIN, em 22/01/2025 às 10:00 UTC. Durante a descida, houve uma falha no sistema de flaps.`
*   **Simular um voo sem ocorrências:** `Simule um voo sem ocorrências para o D-AIHC saindo de MUC em 23/01/2025 às 14:00 UTC com destino a JFK.`
*   **Qual a próxima rota da aeronave:** `Qual a próxima rota do D-AIHU?`

**Regras da Simulação:**

*   **Cronologia:** As datas no log devem ser sempre em ordem cronológica (passado para presente).
*   ***Turnaround*:** Considere um tempo de *turnaround* entre os voos (1-3 horas, dependendo da rota e do aeroporto).
*   **Log Técnico:** O log técnico é um registro *permanente*.
*   **Previsão:** Pedidos de status e próxima rota são *previsões* e não alteram o log.
*   **Ocorrências:** Descreva detalhadamente as ocorrências para que possam ser registradas no log.
*   **Voos sem ocorrências:** Solicite explicitamente a simulação de um voo sem ocorrências para que ele seja registrado no log.

**Exemplo de Log Técnico (D-AIHC - Exemplo Parcial):**

| Aeronave | Data (UTC) | Local | Última Rota | Horário de Pouso (UTC) | Descrição da Ocorrência | Ações Corretivas | Status do MEL | Próxima Manutenção | Manutenção Anterior | Observações |
|---|---|---|---|---|---|---|---|---|---|---|
| D-AIHC | 2025-01-15 14:00 | Em voo (LH505) | GRU-MUC | N/A | Pequena vibração no motor 3. | A ser investigado. | N/A | 15/03/2025 (MUC) | - | Reportado pelo piloto. |
| ... | ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |

**Contribuições:**

Contribuições são bem-vindas! Se você tiver sugestões de melhorias, novas funcionalidades ou correções de bugs, sinta-se à vontade para abrir um *issue* ou enviar um *pull request*.

**Licença:**

[Adicione aqui a licença do seu projeto, como MIT License, por exemplo.]

**Contato:**

[Seu nome/contato]
