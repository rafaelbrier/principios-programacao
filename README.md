# Princípios de Programação

1.  [Solid](#1---solid)\
    1.1 [Princípio da Responsabilidade Única](#11--princpio-da-responsabilidade-nica-srp---s)
    
S. [Bibliografia](#s---bibliografia)


## 1. SOLID

SOLID é um acrônimo dos cinco primeiros princípios da programação orientada a objetos.

### 1.1 Princípio da Responsabilidade Única (SRP) - [S]

***Uma classe deve ter um, e apenas um, motivo para ser modificada***

Se uma classe só deve ter um motivo para ser modificada, certamente ela só deve ter uma única responsabilidade, logo:

Cada **responsabilidade** deve ser uma **classe**, porque uma responsabilidade é um eixo de mudança.

#### Benefícios

* Complexidade do código reduzida, mais explícita e direta
* Facilitação da legibilidade
* Redução de acoplamento
* Código limpo e testável
* Facilidade de evolução

#### Exemplo

A classe abaixo possui três responsabilidades, ou seja, ela tem três razões para ser modificada. Modificar uma das funcionalidades
pode impactar em outras não relacionadas.

![alt text](images/solid1.png)

O correto seria criar três classes, cada qual com uma única responsabilidade.

![alt text](images/solid2.png)

### 2.1 Príncipio Aberto-Fechado (OCP) - [O]

***Entidades de software (classes, módulos, funções, etc) devem estar abertas para extensão, mas fechadas para modificação.***

#### Extensibilidade

É uma das chaves da orientação a objetos, quando um novo comportamento ou funcionalidade precisar ser adicionado é esperado que as existentes sejam estendidas e e não alteradas, assim o código original permanece intacto e confiável enquanto as novas são implementadas através de extensibilidade. Criar código extensível é uma responsabilidade do desenvolvedor maduro, utilizar design duradouro para um software de boa qualidade e manutenibilidade.

#### Abstração

Quando aprendemos sobre orientação a objetos com certeza ouvimos sobre abstração, é ela que permite que este princípio funcione. Se um software possui abstrações bem definidas logo ele estará aberto para extensão.

#### Exemplo

Observe a classe:

![alt text](images/solid3.png)

É uma classe de débito em conta que valida o tipo da conta para aplicar a regra de negócio correta para conta corrente e para conta poupança. Agora vamos supor que surgiu um novo tipo de débito em conta (conta investimento), logo seria necessário modificar a classe.

Se modificarmos a classe colocando mais um IF de validação, além de ter que substituirmos esta classe na publicação da nova versão, corremos o risco de introduzir alguns bugs em uma classe que já estava funcionando.

Além de ter que testar todos os tipos de débito em conta, um bug introduzido nesta modificação não pararia apenas o débito em conta investimento mas poderia causar que todos os tipos de débitos parassem de funcionar.

O correto seria usar abstração para gerar extensibilidade:

![alt text](images/solid4.png)

Veja que possuímos agora uma abstração bem definida, onde todas as extensões implementam suas próprias regras de negócio sem necessidade de modificar uma funcionalidade devido mudança ou inclusão de outra.

O tipo de débito em conta de investimento foi implementado sem modificar nada, usando apenas a extensão. Além de tudo o código está muito mais bonito, entendível e fácil para aplicar cobertura de testes de unidade. Vale mencionar que também está de acordo com o primeiro princípio do SOLID o SRP

#### Conclusão

Este princípio nos atenta para um melhor design, tornando o software mais extensível e facilitando sua evolução sem afetar a qualidade do que já está desenvolvido.

Para o uso do Open Closed Principle é muito comum utilizarmos o Strategy Pattern.

## S.   Bibliografia

* [SOLID](https://www.eduardopires.net.br/2013/04/orientacao-a-objeto-solid/)



