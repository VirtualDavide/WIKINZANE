2025-03-21 11:08

Tags : [[Java]] [[ServerSideDevelopment]]

# Connessione Database - Servlet

La connessione di una servlet Java a un database è un processo fondamentale per le applicazioni web che necessitano di interagire con dati persistenti. Di seguito, descriverò i passaggi necessari e gli oggetti coinvolti in questo processo.
### Passaggi per la Connessione di una Servlet a un Database

1. **Caricamento del Driver JDBC**: Prima di stabilire una connessione al database, è necessario caricare il driver JDBC appropriato. Questo driver consente alla servlet di comunicare con il database specifico (ad esempio, MySQL, PostgreSQL, Oracle, ecc.).
    
2. **Stabilire la Connessione**: Utilizzando la classe `DriverManager`, si stabilisce una connessione al database fornendo l'URL del database, il nome utente e la password.
    
3. **Creazione di un Oggetto Statement**: Una volta stabilita la connessione, si crea un oggetto `Statement` o `PreparedStatement` per eseguire query SQL.
    
4. **Esecuzione della Query**: Utilizzando l'oggetto `Statement`, si esegue la query SQL desiderata (ad esempio, SELECT, INSERT, UPDATE, DELETE).
    
5. **Elaborazione dei Risultati**: Se la query restituisce risultati (come nel caso di una SELECT), si utilizza un oggetto `ResultSet` per elaborare i dati restituiti.
    
6. **Chiusura delle Risorse**: Dopo aver completato le operazioni, è importante chiudere il `ResultSet`, il `Statement` e la `Connection` per liberare le risorse.

*esempio di codice* : 

```Java
import java.io.IOException;
import java.io.PrintWriter;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

@WebServlet("/DatabaseServlet")
public class DatabaseServlet extends HttpServlet {
    private static final long serialVersionUID = 1L;

    protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        String jdbcURL = "jdbc:mysql://localhost:3306/yourdatabase";
        String dbUser = "username";
        String dbPassword = "password";

        Connection connection = null;
        PreparedStatement statement = null;
        ResultSet resultSet = null;

        try {
            // Caricamento del driver JDBC
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Stabilire la connessione
            connection = DriverManager.getConnection(jdbcURL, dbUser, dbPassword);

            // Creazione di un oggetto PreparedStatement
            String sql = "SELECT * FROM yourtable";
            statement = connection.prepareStatement(sql);

            // Esecuzione della query
            resultSet = statement.executeQuery();

            // Elaborazione dei risultati
            PrintWriter out = response.getWriter();
            while (resultSet.next()) {
                out.println("Colonna1: " + resultSet.getString("colonna1"));
                out.println("Colonna2:
				                out.println("Colonna2: " + resultSet.getString("colonna2"));
                out.println("<br>");
            }
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            // Chiusura delle risorse
            try {
                if (resultSet != null) {
                    resultSet.close();
                }
                if (statement != null) {
                    statement.close();
                }
                if (connection != null) {
                    connection.close();
                }
            } catch (Exception e) {
                e.printStackTrace();
            }
        }
    }
}
```
## References

- [[Servlet]]