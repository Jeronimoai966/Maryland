import java.util.Scanner;

public class InformacionPersonal {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

       
        System.out.println("¡Hola! Por favor, ayudame a conocerte mejor :)");
        
        System.out.println("\n¿Cual es tu nombre?");
        String nombre = scanner.nextLine();
        
        System.out.println("\n¿que edad tienes, " + nombre + "?");
        int edad = scanner.nextInt();
        
        System.out.println("\n¿Cual es tu estatura en metros? (ejemplo: 1.75)");
        double estatura = scanner.nextDouble();
        
        scanner.nextLine(); // Limpiar buffer
        System.out.println("\n¿Cual es la inicial de tu nombre?");
        char inicial = scanner.nextLine().charAt(0);
        
        System.out.println("\n¿Eres estudiante? (si/no)");
        boolean esEstudiante = scanner.nextLine().toLowerCase().startsWith("s");

        // Mostrar resumen
        System.out.println("\n--- Informacion Personal ---");
        System.out.println("Nombre: " + nombre);
        System.out.println("Edad: " + edad + " anos");
        System.out.println("Estatura: " + estatura + " metros");
        System.out.println("Inicial: " + inicial);
        System.out.println("Estudiante: " + (esEstudiante ? "Si" : "No"));

        // Solicitar y mostrar calificaciones
        System.out.println("\n--- Registro de Calificaciones ---");
        int[] notas = new int[5];
        double suma = 0;
        
        for (int i = 0; i < notas.length; i++) {
            System.out.print("Ingresa la calificacion " + (i+1) + ": ");
            notas[i] = scanner.nextInt();
            suma += notas[i];
        }

        // Mostrar calificaciones y promedio
        System.out.println("\n--- Resumen de Calificaciones ---");
        for (int i = 0; i < notas.length; i++) {
            System.out.println("Calificacion " + (i+1) + ": " + notas[i]);
        }

        double promedio = suma / notas.length;
        System.out.println("\nPromedio final: " + promedio);
        
        // Mensaje segun el promedio
        if (promedio >= 90) {
            System.out.println("¡Excelente desempeno!");
        } else if (promedio >= 70) {
            System.out.println("¡Buen trabajo!");
        } else {
            System.out.println("Necesitas mejorar tus calificaciones.");
        }

        
        scanner.close();
    }
}
