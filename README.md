# Documentação
    package login; 
    
    import java.sql.Connection;
    import java.sql.DriverManager;
    import java.sql.ResultSet;
    import java.sql.Statment;

    /**
      * Inicia a classe User
    */
    
    public class User{
      /** Cria uma conexão com o banco de dados
        * Retorna a conexão com banco de dados
        */
        
        public Connection conectarBD(){
          /** 
            * Inicia a conexão com o banco de dados como null/Nula
          */
          
            Connection conn = null;
            /** 
              * Usa o método try para realizar a conexão com o banco de dados
            */
            try{
            /**
              * Carrega o banco de dados MYsql
            */
                *Class.forName("com.mysql.Driver.Manager").newInstance();
                
            /** 
              * Caminho para o banco de dados
            */
                String url = "jdbc:mysql://127.0.0.1/test?user=lopes&password=123";
                
            /**  
              * Realiza a conn/conexão com o banco de dados
            */
                conn = DriverManager.getConnection(url);
                
            } 
            /**
              * Tratamento de exceção caso ocorra na conexão com o banco de dados
            */
            catch (Exception e) { }
            /**
              * Retorna a conexão com o banco de dados
              */
            return conn; }
            /**
              * Nome de usuario
              */
    public String nome= "";
    /**
      * Busca Usuario no banco de dados que retorne o result como false
      */
    public boolean result = false;
    /**
     * Verifica se o usuario já esta registrado no banco de dados
     * 
     * @param login
     * @param senha
     * @return 
     */
    public boolean verificarUsuario (String login, String senha){
        /**
         * Faz com que a variavel sql seja iniciada vazia para depois realizara busca do usuario
         */
        String sql = "";
        /**
         * 
         */
        /**
         * Conecta com o banco de dados
         */
        Connection conn = conectarBD();
        /**
         * Monta um select para realizar a busca no banco de dados
         */
        sql += "select nome from usuarios";
        sql += "where login = " + "'" + login + "'";
        sql += "and senha = " + "'" + senha + "';";
        /**
         * Busca o Usuario pela variavel pela variavel sql usada anteriormente
         */
        try{
            /**
             * Inicia as variaveis para buscar no banco de dados e pega o resultado da pesquisa
             */
            Statment st = conn.createStatement();
            ResultSet rs = st.executeQuery(sql);
            /**
             * Se o usuario não seja encontrado o if será executado
             */
            if (rs.next()){
                /**
                 * A variavel result recebe o valor true
                 * Variavel nome recebe o nome encontrado pelo banco de dados
                 */
                result = true;
                nome = rs.getString("nome");}
            
        }
        /**
         * Tratamento de exceção caso haja algo fora dos conformes na busco do registro de usuario pelo banco de dados
         */
        catch (Exception e) { }
        /**
         * Retorna a variavel result
         */
    return result;}
}

