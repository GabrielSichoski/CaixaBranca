# CaixaBranca

## Codigo


    1.package login; 
    
    1.import java.sql.Connection;
    1.import java.sql.DriverManager;
    1.import java.sql.ResultSet;
    1.import java.sql.Statment;
    
    2.public class User{
        3.public Connection conectarBD(){
            4.	Connection conn = null;
            5.try{
               6. Class.forName("com.mysql.Driver.Manager").newInstance();
                6.String url = "jdbc:mysql://127.0.0.1/test?user=lopes&password=123";
                6. conn = DriverManager.getConnection(url);
            7.}  8. catch 9. (Exception e) { } 
           10. return conn; 
    11.}
    12.public String nome= "";
    12.public boolean result = false;
    13. public boolean verificarUsuario (String login, String senha){
        14. String sql = "";
        14.Connection conn = conectarBD();
    
        14. sql += "select nome from usuarios";
        14. sql += "where login = " + "'" + login + "'";
        14. sql += "and senha = " + "'" + senha + "';";
        15 .try{		
            16. Statment st = conn.createStatement();
            16. ResultSet rs = st.executeQuery(sql);
            17. if (rs.next()){
                18.result = true;
                18. nome = rs.getString("nome");
    19.}
        20.} 21.catch  22.(Exception e) { }
        23. return result;}
    24.		

## grafo de fluxo

![image](https://github.com/GabrielSichoski/CaixaBranca/assets/104863390/b6c19e87-a5bf-4ff1-ab24-09c548c2a1bf)

## Complexidade ciclomatica

A complexidade ciclomatica é feito para calcular os caminhos
o calculo é feito por 

 arestas - nós = x

 x + 2 = resultado de caminhos

 Nesse caso são 26 arestas e 24 nós

 26 - 24 = 2


## Caminhos

Caminho 1:
1-2-3-4-5-6-7-10-11-12-13-14-15-16-17-18-19-20-23-24

Neste caminho todas as conexões e pontos dão certo

Caminho 2:

1-2-3-4-5-8-9-10-11-12-13-14-15-16-17-18-19-20-23-24

Neste caminho conectarBD ocorre a excessão e verificar usuario funciona

Caminho 3:

1-2-3-4-5-6-7-10-11-12-13-14-15-21-22-23-24

Neste caminho ocorre a excecão em verificarUsuario

Caminho 4:

1-2-3-4-5-8-9-10-11-12-13-14-15-16-20-23-24

Caminho ocorre a caso não encontre o usuario
