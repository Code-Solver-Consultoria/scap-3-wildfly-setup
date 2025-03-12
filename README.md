# Configuração do Widlfly.

		 
 Scripts de configuração do Wildfly 8.2.1 para o projeto SCAP 3.

 Execute os scripts conforme o exemplo:

	<WILDFLY_HOME>/bin/jboss-cli.sh --connect \
		--user=<username> \
		--password=<password> \
		--file=<file> \
		--properties=<properties>
	Onde:
		<WILDFLY_HOME>: diretório onde o Wildfly está instalado.
		<username>....: nome do usuário de administração do Wildfly. Deve existir em ManagementRealm
		<password>....: senha de confirmação do usuário de administração do Widlfly
		<file>........: script de configuração do Wildfly.
		<properties>..: Arquivo de propriedades com chave e valor (key=value), utilizado para
							passar valores para os scritps. As propriedades são acessíveis com
							o formato ${key}. A entrada properties é condicional. Um exemplo 
							deste arquivo é "env.properites".
		
# Os Scripts

 Os scripts estão sempre em pares, contendo um nome significativo para a funcionalidade que será configurada 
 e um sufixo **add** ou **remove**, com a ação que será executada.
 
## apj
 
 Configura o conector AJP para redirecionamento de informações. Permite ao Apache 2 ser o proxy 
 do aplicativo e disponibilizar a camada WEB protegida na porta 80.
 
## logging
 
 Configura um arquivo de log com o filtro para os métodos e eventos do aplicativo SCAP.
 
## module
 
 Configura um módulo e o torna disponível como parte do sistema para o Wildffly. Como este 
 tipo de script altera o diretório de instalação do Wildfly, este tipo de script deve ser
 executado com usuários com permissão de gravação no diretório <WILDFLY_HOME>/modules.
 
## datasource
 
 Configura uma conexão com um banco de dados. Os drivers para acesso ao banco de dados devem ser disponibilizados como módulos.
