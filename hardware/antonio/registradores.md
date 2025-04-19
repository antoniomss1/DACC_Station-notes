## Arquitetura ARM
Registradores: Os registradores podem ser utilizados para manipular dados de um byte, de meia palavra (16 bits) ou de uma palavra completa (32 bits). Quando instruções de um byte são utilizadas somente o byte menos significativo é utilizado. Quando instruções de meia palavra são utilizadas somente a palavra menos significativa é utilizada. Ao fazer referência a algum destes registros de propósito específico deve-se sempre levar em consideração qual o modo de operação corrente.
#### Registradores

Registradores R0 a R7 são os mesmos em todos os modos de CPU; eles nunca são acumulados.

Registradores R8 a R12 são os mesmos em todos os modos de CPU, exceto no modo FIQ. O modo FIQ possui seus próprios registros R8 a R12.

R13 e R14 são colocados em todos os modos de CPU privilegiados, exceto o modo de sistema. Ou seja, cada modo que pode ser inserido devido a uma exceção tem seu próprio R13 e R14. Esses registradores geralmente contêm o ponteiro da pilha e o endereço de retorno das chamadas de função, respectivamente.

---
O padrão [RISC](https://pt.wikipedia.org/wiki/RISC "RISC") do processador permite que estes processadores tenham menos transístores que processadores CISC ([x86](https://pt.wikipedia.org/wiki/X86 "X86")). Essa abordagem reduz custos, liberação de calor e consumo de energia. Essas são características desejáveis para dispositivos portáteis, como smartphones, laptops, tablets e outros dispositivos embarcados. Uma estrutura mais simples facilita a criação de multi-core CPUs, o que impacta na redução de custos de produção. Os processadores ARM são 90% dos processadores embarcados RISC de 32 bits.
# links