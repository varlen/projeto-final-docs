# Understanding Privacy

## Cap 2

De acordo com Solomon, o conceito de privacidade é formado por uma visão plural com diferentes concepções. O autor pondera que apesar de suas críticas sobre esta metodologia, dadas as limitações individuais de cada concepção, cada uma das facetas da privacidade contribui parcialmente para um entendimento geral. Estas facetas estão listadas a seguir.

### O Direito de Ser Deixado em Paz
(The Right to Be Let Alone)

Instaura que o indivíduo, no que tange a condutas não prejudiciais, tem direito a moldar sua vida como achar melhor, fazer o que quiser e ir aonde quiser. (Pg 17)

### Acesso limitado a si próprio
(Limited Access to the Self)

Essa concepção reconhece o direito do indivudo por distanciamento de outros, incluindo liberdade de interferência governamental e invasões por parte da imprensa e de outros, sendo assim mais sofisticada que a concepção do Direito de Ser Deixado em Paz.

### Sigilo
(Secrecy)

É talvez o entendimento mais comum de privacidade. Sobre essa visão, a privacidade é violada pela divulgação de informação previamente restrita, estando relacionada ao conceito de confidencialidade. Esta faceta da privacidade é limitada pois a maioria dos teóricos reconhece que invasões de privacidade não necessariamente envolvem quebra de sigilo.

### Controle sobre Informações Pessoais
(Control over Personal Information)
TODO - Resumir

### Individualidade
(Personhood)
TODO - Ler e resumir

### Intimidade
(Intimacy)
TODO - Ler e resumir


No escopo deste trabalho, são de maior interesse as facetas de Sigilo e de Controle sobre Informações Pessoais, tanto por seus entendimentos fundamentarem as leis gerais de proteção de dados quanto por fornecerem um insumo tecnologicamente tangível da privacidade.

--> Five Safes Framework
--> PINQ
--> Airavat

## Cap 4 - The Social Value of Privacy - Pg. 89

## Cap 5 - A Taxonomy of Privacy (inteiro) - Pg. 101
Pag 102

As atividades que afetam a privacidade não são inerentemente problematicas. Quando há o consentimento, não há invasão de privacidade.

A taxonomia da privacidade proposta por Solomon tem o objetivo de apoiar a análise de vários problemas de privacidade distintos. Segundo o autor, existem 4 grupos de atividades prejudiciais a privacidade: Coleção de informação, processamento de informação, disseminação de informação e invasão.

Pag 117 - Information Processing

(Essa parte de information processing pode ser usada para os objetivos. Ex: Dificultar e preferencialmente previnir a aplicação das técnicas listadas, protegendo indivíduos e conjuntos de dados sensíveis)


Uso, armazenamento e manipulação de dados previamente coletados. Não involve a coleta de dados. Solomon discute 5 formas de processamento:
Agregação, identificação, inseguraça, uso secundário e exclusão.

Agregação
"O todo é maior que a soma das partes"

Agregação é a junção de informações sobre um indivíduo. Informações de diversas fontes isoladas não costumam ser críticas, porém unidas podem gerar o perfil de um indivíduo, possibilitando um ataque de deanonimização.
Quando analisadas, as informações agregadas podem revelar fatos sobre
um indivíduo cuja revelação não era esperada quando as informações isoladas originais foram coletadas.

Identificação

De acordo com Roger Clarke, identificação é a associação de informações a um indivíduo em particular. Identificação se assemelha a agregação no sentido da associação de informações. A diferença entre essas formas de processamento de informações aparece na obrigatoriedade da associação das informações conhecidas com uma única pessoa específica e conhecida.

Insecurity

Secondary Use

Exclusion


## Cap 6 - The Future of Privacy - Pg. 196


# Metodologia

### ARX - Open Source Data Anonymization Software

", the effectiveness of different anonymization techniques depends
on context, and thus tools need to support a large set of methods to ensure
that the usefulness of data is not overly affected by risk-reducing transformations"

"The basic idea is to
transform data in such a way that privacy risks are reduced while the reduction of risks is balanced against a reduction of
data utility"

"More formal approaches are required, which employ mathematical and statistical models for quantifying risks and the impact of anonymization on data usefulness."

"We note that formal data anonymization is
different from basic techniques of data masking or random data generation.19 In this work, we focus on non-interactive
microdata anonymization, which means that protected records are created from the records of an input dataset"

( Reescrever os paragrafos a seguir para dentro da descrição do ARX)
Processo:
    Remoção das informações que possam identificar diretamente os individuos. A seguir, modificar o conjunto de dados de maneira a balancear o risco de um atacante conseguir associar um registro a um individuo ou a outras informações sensíveis e a utilidade do conjunto de dados modificado. O risco de brechas de privacidade pode ser quantificado por modelos matemáticos de privacidade (privacy models) assim como a utilidade (por utility models). Esses modelos geralmente utilizam um limiar para definir o nível de risco aceitável.
    Idealmente, realiza-se então um processo iterativo de busca por todo espaço de saídas possíveis, definidas por uma ou mais transformações, para encontrar uma solução ótima tanto do limiar de risco quanto para utilidade.

    Uma transformação pode envolver processos como substituir valores específicos de um conjunto pela média, tomar amostras aleatórias dos registros iniciais, suprimir valores individuais, mascarar partes de sequências de caracteres, categorizar atributos numéricos (ex: Peso 75 kg -> Peso 70~80 kg), ou generalização de informações categoricas (Ex: Substituir rua por bairro). Essas transformações introduzem ruídos e incertezas que reduzem o risco de ataques de deanonimização por correspondência dos dados.

    Como o espaço de busca da solução ótima desse problema é geralmente muito amplo para ser implementado, utilizam-se estratégias heuristicas e algoritmos de clustering. 

    A efetividade das diferentes tecnicas de anonimização depende do contexto em que são aplicadas, incluindo a dimensionalidade, volume e propriedades estatisticas dos dados. Também deve-se considerar a quais aplicações os dados serão utilizados e se serão disponibilizados publicamente, além de características transacionais dos dados. Presume-se que o software de anonimização seja utilizado em cenários diversos. Por isso, é importante a implementação de diferentes métodos de anonimização e quantificação da redução de utilidade. Além disso, muitas tecnicas de anonimização involvem uma significativa complexidade computacional, tornando um desafio sua implementação de maneira escalável.

---


( Neste ponto pode ser interessante adicionar uma ilustração deste esquema de funcionamento do ARX para fixar os conceitos)

O usuário pode determinar o número máximo de registros que pode ser suprimido. Além disso, também é possível determinar se todos os registros serão transformados da mesma forma ou particionar o conjunto de registros para utilização de transformações diferentes por subconjunto de dados. Outra funcionalidade presente no ARX é a amostragem de dados do conjunto de entrada, tanto aleatoriamente quanto por uma consulta específica.


[Esse paragrafo inteiro não está muito bom, muito parecido com o texto original]
Os modelos de privacidade do ARX englobam diferentes ameaças como "membership disclosure" (a exposição de que um indivíduo pertence a um grupo), "attribute disclosure" e "identity disclosure" [11 - Introduction to Privacy-Preserving Data Publishing: Concepts and Techniques]. 

Os modelos de privacidade também incluem diferentes perfis de atacantes, cada um com suas intenções específicas, como "promotor", "jornalista" e "marketeiro". [67 - Anonymizing Health Data: Case Studies and Methods to Get You Started.] Modelos sintáticos garantem restrições estruturais nos dados assim como modelos estatisticos estimam a probabilidade de sucesso de determinados ataques. Modelos semânticos tem relação direta com noções matemáticas de privacidade.

( É interessante ler mais sobre esses modelos de ataque para dissertar e incluir no texto )




? Como são carregados os dados no programa?



Continua...

#### TODO - Escrever sobre a questão da consistência dos dados após a transformação em alguns casos, dependendo da tecnica aplicada. (Parafraseando o "Data Intensive Applications", Consistência geralmente é uma responsabilidade da aplicação e não do Banco de Dados). A transformação não têm como garantir que a integridade das relações do banco sejam suficientes para consistência a nivel de aplicação. Ou tem?


##### TODO - Adicionar um desenho com o fluxograma de processos das diferentes soluções (pag 2 do paper da wiley EICHER ET AL. sobre o ARX, para os outros, será necessário fazer a imagem)










-----

## Gloassário 

Registro - Unidade de armazenamento de dados estruturados. No caso de um banco de dados relacional, um registro é especificamente uma linha de uma tabela.

Atributo - Um campo presente em registros de uma mesma entidade. A implementação relacional do atributo é a coluna de uma tabela.

Célula - Valor de um atributo em um registro específico

Dimensionalidade - Número de atributos

Volume - Número de registros

Linguagem Específica de Domínio - (...)

Mapeador Objeto Relacional - (...)
## Arquitetura

Inspetor de Estrutura - Componente responsável por extrair a estrutura do banco de dados relacional a ser anonimizado, tabelas, colunas, tipos de armazenamento, tipos semânticos (classificação de entidades), estatisticas de agregação e relações.
-> Pesquisar sobre "classificação de dados" para melhorar essas nomeclaturas aqui.

Estrutura de Anonimização - Arquivo que armazena os dados extraídos pelo inspetor de estrutura, dados de conexão com o banco de dados e origens de registro para utilização futura.

Interface de Usuário - Permite parametrizar o inspetor de estrutura para gerar origens de registro específicas

Origem de Registro - Componente responsável por definir as regras utilizadas para popular as tabelas do banco de dados anonimizado. Cada tabela da estrutura extraída deve ser associada a uma coleção destes componentes. 

Uma Origem de Registro pode ser:
    - a transformação de um conjunto de registros (linhas) originais com colunas suprimidas e/ou generalizadas. É realizada uma operação de mapping entre o registro original e o registro anonimizado. Nesse caso, é necessário acesso ao banco original para execução da estrutura de anonimização.
    - a regra para geração de um registro aleatório a partir do conhecimento dos tipos semânticos e relações da tabela original. Nesse caso, não é necessário acesso ao banco original para popular a tabela.

