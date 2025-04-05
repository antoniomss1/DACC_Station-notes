## 1. **Herança/Implementação (--▷ Seta tracejada com ponta vazia):**
    
- LaunchCommand **é um tipo de** Command.
    
- StopCommand **é um tipo de** Command.
    
- NotInstalledState, InstalledState, RunningState **são tipos de** GameState.
    
- **O que significa:** As classes "filhas" (ex: LaunchCommand) prometem ter todos os métodos definidos na classe "mãe" abstrata ou interface (ex: Command). Isso permite tratar todos os comandos (ou todos os estados) da mesma forma genérica **(polimorfismo).** O CommandInvoker só precisa saber que tem um Command*, não importa se é LaunchCommand ou StopCommand. O Game só precisa saber que tem um GameState*.
    
## 2. **Associação/Dependência (-> Seta sólida ou --> Seta tracejada):** Indica que uma classe usa outra.
    
- LaunchCommand e StopCommand **usam/dependem de** Game (game : Game*). Elas precisam saber qual jogo devem iniciar ou parar. Geralmente, o objeto Game é passado para o construtor do comando.
        
- CommandInvoker **usa** Command (através da commandQueue) e **usa/cria** WorkerThread. O Invoker gerencia a fila de comandos e inicia a thread que vai processá-los.
        
- WorkerThread **usa** Command (pega da fila e chama execute()).
        
- Game **usa/depende de** ProcessManager (Game --> ProcessManager). Para iniciar/parar o processo real, o Game (ou mais precisamente, seu estado atual) precisará chamar métodos do ProcessManager.
        
- Os Estados Concretos (InstalledState, RunningState, etc.) **usam/dependem de** Game. Veja os parâmetros launch(game : Game*). Eles precisam do objeto Game para, por exemplo, mudar o estado desse jogo (game->setState(...)) ou obter informações como o caminho do executável.
        
- Os Estados Concretos (InstalledState, RunningState) **usam/dependem de** ProcessManager (implícito, não desenhado diretamente de cada estado, mas é onde a lógica de startProcess/stopProcess será chamada).
        
## 3. **Composição/Agregação (◆- Linha com losango):** Indica que uma classe contém ou é composta por outra (relação "tem um").
    
- Game **tem um** GameState (currentState : GameState*). Esta é a relação chave do padrão State. O objeto Game possui um objeto que representa seu estado atual. Quando uma ação (launch(), stop()) é chamada no Game, ele delega essa ação para o currentState.
#DACC-Station #Software #Feliph #Topicos01 