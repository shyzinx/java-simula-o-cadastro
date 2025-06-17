import java.io.FileWriter;
import java.io.IOException;
import java.time.LocalDateTime; // Para pegar data e hora
import java.time.format.DateTimeFormatter; // Para formatar a data/hora

public class RegistroLog {
    public static void main(String[] args) {
        try {
            FileWriter writer = new FileWriter("log.txt", true); // Modo append

            // Simula uma ação de cadastro
            String acao = "Produto cadastrado: Café"; // Ação realizada
            LocalDateTime agora = LocalDateTime.now(); // Pega data e hora atual
            DateTimeFormatter formato = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm"); // Formato personalizado
            String dataHora = agora.format(formato); // Aplica o formato

            writer.write("[" + dataHora + "] " + acao + "\n"); // Grava no arquivo

            writer.close();
            System.out.println("Ação registrada no log.");

        } catch (IOException e) {
            System.out.println("Erro ao registrar log: " + e.getMessage());
        }
    }
}
