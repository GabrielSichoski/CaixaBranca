# CaixaBranca
Introdução
  Com o intuito de estudar qualidade de teste de software, foi proposto pelo professor
  Daniel Ohata a análise de um codigo afim de encontrar erros seja no funcionamento
  ou no modo que o codigo esta ambientando, sendo assim listei os erros que eu
  consegui encontrar.

Exceções
  O codigo faz o uso de exceções porem não descreve qual o tipo de exceção assim
  tornando dificil, caso ocorra algum tipo de erro ter noção do que ocorreu.
  
  ![image](https://github.com/GabrielSichoski/CaixaBranca/assets/104863390/b240ee9c-0803-4d5a-9b71-7babbe853a10)

Segurança banco de dados
  O banco de dados não está seguro tendo em vista que caso algum invasor insira
  o valor '1' = '1' na campo te login ele não terá a acesso ao login, porem
  como '1' = '1' é sempre verdadeiro o invasor pode ter acesso a todas as linhas
  da tabela de usuário no banco de dados, assim tornando facil a invasão.
  
  ![image](https://github.com/GabrielSichoski/CaixaBranca/assets/104863390/35388633-b07e-4d48-a6a1-0af1e5e4864e)
  
Estrutura do codigo
  A estrutura do codigo não é muito favorável e não é comumente usado, como por 
  exemplo o modo que é lançado as informações para o banco de dados sendo bem incomum.

Conexão Banco de dados
  Aparentemente o codigo não mostra a conexão com o banco de dados sendo fechado,
  o que poderia ser feito é usar "null" nas informações/variaveis rs, st e conn. Além
  do uso de variaveis publicas sendo praticamente o codigo inteiro de classes e variaveis publicas.

Conclusão
  Minha conclusão sobre o codigo é ele vai funcionar porém esses erros torna perigoso
  o uso do mesmo, caso o usuário use de forma comum ele funciona, mas caso alguém
  má intencionado tente usar o codigo ele pode causar grandes prejuízo. Neste caso 
  será necessário algumas mudanças, na conexão com o banco de dados, no envio das informações
  para o banco de dados, na estrutura do codigo, e definir melhor as execeções para caso
  de alguma forma não conectar com o banco de dados seja avisado

