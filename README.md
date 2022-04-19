# iaibmclouddata
<h1>Modelos de IA com IBM Cloud Pak for Data</h1>
Este repositório contém o conjunto de dados e as notas/instruções de pré-requisitos necessários para fazer uma demonstração prática ao lado da demonstração do Db2 com WKC & Watson Studio.

<h2>Requisitos</h2>
<h3> Por favor, para um perfeito funcionamento preencha os seguintes requisitos.  </h3>

<p> 1 - Ter um cluster do Cloud Pak for Data (esta demonstração não foi feita para a nuvem pública IBM Cloud) com os serviços Watson Knowledge Catalog e Watson Studio instalados. O Watson Studio já deve ter a instância de machine learning ativada </p>
<p> 2 - Customers.csv já deve ter sido inserido em uma tabela no Db2 </p>

<h2> Fazendo download e carregando o conjunto de dados em uma tabela no Db2 </h2>

<p> Baixe o arquivo Customers.csv localizado neste repositório. Para carregar o conjunto de dados TELCO em sua tabela no Db2  </p>

db2start
db2 connnect to <database_name>

<pre class="notranslate"><code class="notranslate">db2start
db2 connnect to &lt;database_name&gt;


db2 "CREATE TABLE &lt;table_schema&gt;.&lt;table_name&gt;&nbsp; (
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "CUSTOMERID" VARCHAR(20 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "GENDER" VARCHAR(12 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "EMAIL" VARCHAR(60 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "PHONENUMBER" VARCHAR(36 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "SENIORCITIZEN" INTEGER ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "PARTNER" VARCHAR(6 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "DEPENDENTS" VARCHAR(6 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "TENURE" INTEGER ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "PHONESERVICE" VARCHAR(6 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "MULTIPLELINES" VARCHAR(32 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "INTERNETSERVICE" VARCHAR(22 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "ONLINESECURITY" VARCHAR(38 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "ONLINEBACKUP" VARCHAR(38 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "DEVICEPROTECTION" VARCHAR(38 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "TECHSUPPORT" VARCHAR(38 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "STREAMINGTV" VARCHAR(38 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "STREAMINGMOVIES" VARCHAR(38 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "CONTRACT" VARCHAR(28 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "PAPERLESSBILLING" VARCHAR(6 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "PAYMENTMETHOD" VARCHAR(50 OCTETS) ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "MONTHLYCHARGES" DOUBLE ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "TOTALCHARGES" DOUBLE ,
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; "CHURN" VARCHAR(6 OCTETS) );"
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
db2 "IMPORT FROM coCustomers.csv OF DEL skipcount 1 INSERT INTO &lt;table.schema&gt;.&lt;table_name&gt;"
</code></pre>
