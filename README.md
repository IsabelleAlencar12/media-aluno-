import java.util.Scanner;
public class temperatura {
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);
            double[] grades = new double[8];

            // Solicitando as 8 notas do aluno
            System.out.println("Digite as 8 notas anuais do aluno:");
            for (int i = 0; i < 8; i++) {
                System.out.print("Nota " + (i + 1) + ": ");
                try {
                    grades[i] = scanner.nextDouble();
                    // Validando se a nota está entre 0 e 10
                    if (grades[i] < 0 || grades[i] > 10) {
                        System.out.println("Erro: A nota deve estar entre 0 e 10. Tente novamente.");
                        i--; // Volta para repetir a entrada
                    }
                } catch (Exception e) {
                    System.out.println("Erro: Entrada inválida. Digite um número válido.");
                    scanner.next(); // Limpa a entrada inválida
                    i--; // Volta para repetir a entrada
                }
            }

            // Calculando médias bimestrais
            double firstBimester = (grades[0] + grades[1]) / 2;
            double secondBimester = (grades[2] + grades[3]) / 2;
            double thirdBimester = (grades[4] + grades[5]) / 2;
            double fourthBimester = (grades[6] + grades[7]) / 2;

            // Calculando médias semestrais
            double firstSemester = (firstBimester + secondBimester) / 2;
            double secondSemester = (thirdBimester + fourthBimester) / 2;

            // Calculando média final
            double finalAverage = (firstSemester + secondSemester) / 2;

            // Exibindo resultados
            System.out.println("\nResultados:");
            System.out.println("1º Bimestre: " + String.format("%.1f", firstBimester));
            System.out.println("2º Bimestre: " + String.format("%.1f", secondBimester));
            System.out.println("1º Semestre: " + String.format("%.1f", firstSemester));
            System.out.println("3º Bimestre: " + String.format("%.1f", thirdBimester));
            System.out.println("4º Bimestre: " + String.format("%.1f", fourthBimester));
            System.out.println("2º Semestre: " + String.format("%.1f", secondSemester));
            System.out.println("Média Final: " + String.format("%.1f", finalAverage));

            scanner.close();
        }
    }
