# Database-Experience

o papel dos Bancos de Dados Relacionais (SQL) e Não Relacionais (NoSQL) no contexto de um Engenheiro de Dados.

Fonte da pesquisa
https://www.devmedia.com.br/introducao-aos-bancos-de-dados-nosql/26044


Bancos de dados relacionais escalam, mas quanto maior o tamanho, mais custoso se torna essa escalabilidade, seja pelo custo de novas máquinas, seja pelo aumento de especialistas nos bancos de dados utilizados.

Já os não relacionais, permitem uma escalabilidade mais barata e menos trabalhosa, pois não exigem máquinas extremamente poderosas e sua facilidade de manutenção permite que um número menor de profissionais seja necessário.

Assim, os bancos de dados NoSQL, vão ficando mais populares entre as grandes empresas pois reúnem as características de poder trabalhar com dados semi-estruturados ou crus vindos de diversas origens (arquivos de log, web-sites, arquivos multimídia, etc...).

Utilização do processamento paralelo para processamento das informações: para se atingir uma performance razoável no processamento de grandes volumes de dados, é mais eficiente dividir a tarefa em várias outras menores e que podem assim, serem executadas ao mesmo tempo, distribuindo essas tarefas pelos vários processadores disponíveis, para isso, os sistemas precisam atingir um alto grau de maturidade no processamento paralelo.

O uso de muitos processadores baratos, não só oferece melhor performance, mas se torna também uma solução economicamente interessante, pois dessa forma é possível escalar o sistema horizontalmente apenas adicionando hardware e não limita a empresa a poucos fornecedores de hardware mais poderoso.

Distribuição em escala global: para atender seus usuários de forma eficiente, algumas empresas utilizam vários data centers, localizados em diversas partes do pais ou do mundo.

Com isso, uma série de questões sobre disponibilidade e performance são levantadas ao construir os sistemas.

A distribuição deles combinada com o hardware barato, impõe ao sistema a necessidade de ser robusto o suficiente para tolerar falhas constantes e imprevisíveis, seja de hardware, seja da infraestrutura do lugar onde o data center se encontra.

Pensando nessas questões, bem como nas necessidades internas ou dos clientes, foi surgindo uma grande quantidade de bancos de dados não relacionais de trabalham de diferentes maneiras

Banco de dados que trabalham no esquema chave/valor (Key/Value): sistemas distribuídos nessa categoria, também conhecidos como tabelas de hash distribuídas, armazenam objetos indexados por chaves, e possibilitam a busca por esses objetos a partir de suas chaves.

Alguns bancos que utilizam esse padrão são: DynamoDb, Couchbase, Riak, Azure Table Storage, Redis, Tokyo Cabinet, Berkeley DB, etc...

Bancos de dados orientados a documentos: os documentos dos bancos dessa categoria, são coleções de atributos e valores, onde um atributo pode ser multi-valorado. Em geral, os bancos de dados orientados a documento não possuem esquema, ou seja, os documentos armazenados não precisam possuir estrutura em comum.

Essa característica faz deles boas opções para o armazenamento de dados semi estruturados.

Alguns bancos que utilizam esse padrão são: MongoDb, CouchDB, RavenDb, etc.

Bancos de dados de famílias de colunas : Bancos relacionais normalmente guardam os registros das tabelas contiguamente no disco. Por exemplo, caso se queira guardar id, nome e endereço de usuários em um sistema de cadastro, os registros seriam: Id1, Nome1, Endereço1; Id2, Nome2, Endereço2.

Essa estrutura torna a escrita muito rápida, pois todos os dados de um registro são colocados no disco com uma única escrita no banco. Essa estrutura também é eficiente caso se queira ler registros inteiros. Mas para situações onde se quer ler algumas poucas colunas de muitos registros, essa estrutura é pouco eficiente, pois muitos blocos do disco terão de ser lidos. Para esses casos onde se quer otimizar a leitura de dados estruturados, bancos de dados de famílias de colunas são mais interessantes, pois eles guardam os dados contiguamente por coluna.

O exemplo anterior em um banco de dados dessa categoria ficaria: Id1, Id2; Nome1, Nome2; Endereço1, Endereço2.

Por esse exemplo é possível perceber a desvantagem de um banco de dados de famílias de colunas: a escrita de um novo registro é bem mais custosa do que em um banco de dados tradicional. Assim, num primeiro momento, os bancos tradicionais são mais adequados aprocessamento de transações online (OLTP) enquanto os bancos de dados de famílias de

colunas são mais interessantes para processamento analítico online (OLAP). O Bigtable é uma implementação da Google dessa categoria de bancos de dados . Outros bancos de dados que são orientados a coluna: Hadoop, Cassanda, Hypertable, Amazon SimpleDB, etc. Bancos de dados de grafos: diferentemente de outros tipos de bancos de dados NoSQL, esse está diretamente relacionado a um modelo de dados estabelecido, o modelo de grafos. A ideia desse modelo é representar os dados e / ou o esquema dos dados como grafos dirigidos, ou como estruturas que generalizem a noção de grafos .

O modelo de grafos é mais interessante que outros quando “informações sobre a inter-conectividade ou a topologia dos dados são mais importantes, ou tão importante quantos os dados propriamente ditos . O modelo orientado a grafos possui três componentes básicos: os nós (são os vértices do grafo), os relacionamentos (são as arestas) e as propriedades (ou atributos) dos nós e relacionamentos.

Neste caso, o banco de dados pode ser visto como um multigrafo rotulado e direcionado, onde cada par de nós pode ser conectado por mais de uma aresta. Um exemplo pode ser : “Quais cidades foram visitadas anteriormente (seja residindo ou viajando) por pessoas que viajaram para o Rio de Janeiro ?” No modelo relacional esta consulta poderia ser muito complexa devido a necessidade de múltiplas junções, o que poderia acarretar uma diminuição no desempenho da aplicação. Porém, por meio dos relacionamentos inerentes aos grafos, estas consultas tornam-se mais simples e diretas.

Alguns bancos que utilizam esse padrão são: Neo4J, Infinite Graph, InforGrid, HyperGraphDB, etc. Como podem ver, os bancos de dados que se utilizam do conceito NoSQL, abrangem uma ampla gama de possibilidades de armazenamento da informação. Veremos no próximo artigo porque ele tem sido considerado fundamental para o BigData, e como podemos tirar partido de seu potencial.
