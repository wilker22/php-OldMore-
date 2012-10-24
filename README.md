php OldMore
============

Sistema baseado em cakephp e um pouco de Opencart.  
Sistema busca fazer busca em banco de dados simples e eficiente. 


Configurando banco de dados
============
Todas as tabelas no banco de dados devem ser em letras minusculas para não dar 
comflito com funções do sistema.

Para configurar o banco de dados você deve entrar na seguinte pasta library e abrir o arquivo config.php
library/config.php


Execudando sistema
============
Em todos as paginas que você queira o sistema funcionando você deve chamar o arquivo library.php 
que se encontra dentro da pasta "library" segue um exemplo abaixo.

require_once "library/library.php";

Para chamar as funções você vai usar a seguinte variavel "M::$C->" ou utilizar a valiavel "$This->" e em 
seguida o nome da tabela.


Busca de um campo
============
Para fazer um busca o simples

$This->nome da tabela("função que vc quer usar",array("coluna da tabela"=>"oque você quer pesquisar","coluna da tabela"=>"oque você quer pesquisar"));

Resposta da Funcao
============
A Resposta da função sempre fica dentro da variavel "M::$C->reposta" ou "$This->reposta"


Lista de Funcoes
============
-pesquisar  ("pesquisar",array("coluna"=>"oque pesquisar","coluna"=>"oque pesquisar","coluna"=>"oque pesquisar"))

-alterar	("alterar",array("coluna tabela"=>"oque alterar"),array("coluna tabela" => "valor a ser alterado"))

-salvar		("salvar",array("coluna tabela"=>"valor a ser salvo","coluna tabela"=>"valor a ser salvo"))

-excluir	("excluir",array("coluna"=>"oque pesquisar","coluna"=>"oque pesquisar","coluna"=>"oque pesquisar")) apois pesquisasr ele vai excluir


Ex:
============
M::$C->tbl_psicologo("pesquisar",array("nome"=>"novo teste"));

ou

$This->tbl_psicologo("pesquisar",array("nome"=>"novo teste"));

Resposta

pr(M::$C->reposta);

ou

pr($This->reposta);

<?php
	foreach($This->reposta as $resp)
	{

		echo $resp;
		
	}
?>

SELECT  * FROM tbl_psicologo  WHERE nome = 'novo teste'
