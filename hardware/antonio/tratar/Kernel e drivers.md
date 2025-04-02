kernel - interface hardware e software
	- monolítico
	- microkernel
	- hibrido
		  Windows 10, por exemplo
	- exokernel

Kernel é a parte do SI que gerencia os recursos

### **Componentes de um SO:**

✔️ **Kernel** – Gerencia o hardware e os recursos.  
✔️ **Drivers** – Permitem que o SO use dispositivos como impressoras, placas de vídeo, etc.  
✔️ **Interface Gráfica (GUI)** – O ambiente visual que o usuário interage.  
✔️ **Shell / Linha de Comando (CLI)** – Permite comandos diretos ao sistema.  
✔️ **Serviços do sistema** – Como gerenciamento de arquivos, rede e autenticação de usuários.

### de https://learn.microsoft.com/pt-br/windows-hardware/drivers/gettingstarted/user-mode-and-kernel-mode

Quando você inicia um aplicativo no modo de usuário, o Windows cria um _processo_ para ele. Esse processo fornece ao aplicativo um espaço de [_endereço virtual_](https://learn.microsoft.com/pt-br/windows-hardware/drivers/gettingstarted/virtual-address-spaces) privado e uma _tabela de identificador_ privado.

Todo o código em execução no modo kernel compartilha um único [espaço de endereço virtual](https://learn.microsoft.com/pt-br/windows-hardware/drivers/gettingstarted/virtual-address-spaces). Como resultado, um driver no modo kernel não é isolado de outros drivers ou do sistema operacional.