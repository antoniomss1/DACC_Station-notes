### Perguntas:
- Quais as possibilidades de tecnologias de comunicação entre o console e o controle que podemos utilizar?
- Qual a tecnologia mais adequada? Das opções:
	- Uma antena PCB trace pode ser uma escolha interessante considerando o tempo que temos e suas possibilidades de otimização. Seria viável criar uma apesar de sua maior complexidade?
	- Um ESP 01S é a opção disponível atualmente, mas estamos considerando o quão necessário seria um, e pesquisando outro possível microcontrolador que já permitisse o controle dos botões e analógicos. Um ESP 01S é capaz de suprir essas necessidades?
	- Outra possibilidade interessante é alguma tecnologia bluetooth. Aparentemente já é a tecnologia usada por outros controles, e tem um bom suporte da comunidade de devs, 
- Tem como nós mesmos desenvolvermos nosso microcontrolador por encomenda? ou um microprocessador?
- O que são as arquiteturas dos microcontroladores? Como a Harvard e a Von Neumann (microprocessadores nesse caso)?
- O que são Bit fuses?
### Ver melhor
- ~~processadores DSP (processador digital de sinal)
- Microcontroladores PIC
	16f876
	18f
	40 pinos
	12f
	24f
		site da microchip: https://www.microchip.com/ ->produtos ->microcontroladores
		tools ->MPLAB X (IDE)
		Compilador XC 8
### Resumo do que foi feito no dia
- Pesquisa sobre o básico do funcionamento de dispositivos bluetooth
- Avaliação dessas tecnologias
- Decidindo sobre qual tecnologia será usada para realizar a comunicação sem fio do controle e do console. Opções:
	- PCB antenna
		Ver sobre: KiCad, DipTrace (softwares para desenhar)
	- módulo Bluetooth
	- ESP 32 ou ESP 01S
- 