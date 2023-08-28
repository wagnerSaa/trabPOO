Estratégia para Construção do Sistema de Controle de Despesas
1. Estrutura de Diretórios
O projeto será organizado em três principais diretórios:

src: Este diretório conterá o código-fonte do sistema, onde as classes e funcionalidades serão implementadas.
data: Neste diretório, os arquivos de dados, como despesas, tipos de despesa e usuários, serão armazenados.
docs: O diretório de documentação conterá informações adicionais sobre o projeto, se necessário.
2. Classes e Funcionalidades
Classe Main
A classe Main conterá o ponto de entrada do programa e será responsável por coordenar a interação com o usuário.

Classe MenuPrincipal
A classe MenuPrincipal exibirá o menu principal para o usuário, permitindo que ele escolha as diferentes funcionalidades do sistema.

Classe Despesa (Classe Abstrata)
A classe Despesa será uma classe abstrata que conterá os atributos e métodos comuns a todas as despesas, como descrição, valor, data de vencimento e categoria. Também implementará a interface "Pagável" para permitir o registro de pagamentos.

Classe CategoriaDespesa
A classe CategoriaDespesa representará as diferentes categorias de despesa, herdando da classe Despesa. Cada categoria terá métodos específicos de acordo com suas características.

Classe TipoDespesa
A classe TipoDespesa permitirá o gerenciamento dos tipos de despesa. Será possível criar, editar, listar e excluir tipos de despesa. As informações serão armazenadas em um arquivo de texto separado.

Classe Usuario
A classe Usuario será responsável pelo gerenciamento de usuários do sistema. Ela permitirá cadastrar, editar e listar usuários, incluindo a criptografia das senhas antes do armazenamento.

Classe ManipuladorArquivo
A classe ManipuladorArquivo fornecerá métodos para lidar com a leitura e escrita de informações nos arquivos de dados, como despesas, tipos de despesa e usuários.

Classe MenuListagemDespesas
A classe MenuListagemDespesas possibilitará a listagem de despesas em aberto ou pagas, com opções de filtrar por período, status e categoria. Após listar, permitirá editar ou excluir despesas.

Interface Pagável
A interface Pagável definirá o contrato para a anotação de pagamentos em uma despesa. Será implementada pelas classes de despesa.

3. Fluxo de Execução
O programa começará na classe Main, onde instâncias das classes MenuPrincipal, TipoDespesa, Usuario e ManipuladorArquivo serão criadas. O MenuPrincipal será exibido, permitindo que o usuário escolha as funcionalidades desejadas. Cada funcionalidade será implementada de acordo com a lógica específica de cada classe, interagindo com as instâncias criadas.

4. Documentação
A documentação será abordada de duas maneiras:

README.md: O arquivo README.md conterá uma descrição geral do projeto, instruções para a execução do sistema e uma visão geral das classes e funcionalidades.
Documentação das Classes: Cada classe será documentada com informações sobre seus atributos, métodos e exemplos de uso. Essas informações poderão estar diretamente no README ou em arquivos separados, que serão linkados no README.



Classe Main
A classe Main pode conter o método main para iniciar a execução do programa.

Classe MenuPrincipal
Atributos:

Nenhum atributo específico.
Métodos:

exibirMenu(): Exibe as opções do menu principal e aguarda a entrada do usuário.
realizarAcao(opcao): Realiza a ação correspondente à opção escolhida pelo usuário.
Classe Despesa (Classe Abstrata)
Atributos:

descricao: string
valor: float
dataVencimento: string
categoria: CategoriaDespesa
statusPago: bool
Métodos:

getDescricao()
setDescricao(descricao)
getValor()
setValor(valor)
getDataVencimento()
setDataVencimento(data)
getCategoria()
setCategoria(categoria)
getStatusPago()
setStatusPago(pago)
registrarPagamento(dataPagamento, valorPagamento)
Classe CategoriaDespesa
Métodos:

Métodos específicos para categorias de despesa, como calcularJuros() para despesas com juros.
Classe TipoDespesa
Métodos:

criarTipoDespesa(nome)
editarTipoDespesa(nome, novoNome)
listarTiposDespesa()
excluirTipoDespesa(nome)
Classe Usuario
Atributos:

login: string
senha: string (que será criptografada)
Métodos:

cadastrarUsuario(login, senha)
editarUsuario(login, novaSenha)
listarUsuarios()
criptografarSenha(senha)
Classe ManipuladorArquivo
Métodos:

lerArquivo(nomeArquivo): Lê um arquivo de dados e retorna o conteúdo.
escreverArquivo(nomeArquivo, conteudo): Escreve o conteúdo em um arquivo de dados.
Classe MenuListagemDespesas
Métodos:

listarDespesasAberto(periodo)
listarDespesasPagas(periodo)
filtrarDespesasPorStatus(despesas, pago)
filtrarDespesasPorCategoria(despesas, categoria)
exibirSubMenu(despesas)
Interface Pagável
Métodos:

registrarPagamento(dataPagamento, valorPagamento)
