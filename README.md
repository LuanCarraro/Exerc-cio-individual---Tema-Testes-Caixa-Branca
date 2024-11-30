# Exercicio-individual---Tema-Testes-Caixa-Branca

Ao longo deste código foram encontrados possiveis erros no código. São eles:

1. Conexão não fechada - A conexão com o banco de dados é aberta na nona linha do código mas jamais é fechada. Este erro resulta em conexões desnecessárias abertas, o que pode levar a utiilização excessiva de memória e processamento. Além disso, caso o número de conexões abertas exceder o suportado pelo banco de dados, o acesso ao banco será impossibilitado.
2. Tratamento incompleto de erros - No bloco "catch (Exception e) { }", tanto na linha 15 quanto na linha 32, o erro é "pego" pelo código, mas nada é feito com ele. O possivel erro não é tratado dentro do bloco e, além disso, também não é exibida nenhuma mensagem explicitando o erro, dificultando sua identificação e correção.
3. Injeção SQL - Na linhas 24 e 25, login e senha são inseridos diretamente na querySQL, abrindo espaço para que um usuário mal intencionado insira comandos SQL arbitrários e tenha acesso à dados sigilosos.
4. Credenciais expostas - Na linha 13, as credenciais "user" e "password", utilizadas para acessar o banco de dados, estão expostas diretamente no código, possibilitando que qualquer um que tenha acesso ao código também tenha acesso às credenciais. Desta forma, possíveis invasores teriam o acesso à essas informações facilitado.
5. Não validação de variáveis - As váriaveis "login" e "senha" não são validadas em nenhum momento. Assim, valores inválidos, como "null" , poderiam gerar erros ou comportamento imprevisível. 
