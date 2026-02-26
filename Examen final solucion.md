Est**ructura de carpetas (recomendada)**

```
ProyectoTickets/
└─ src/
   ├─ Main.java
   ├─ models/
   │  ├─ Ticket.java
   │  └─ Usuario.java
   └─ utils/
      └─ InputHelper.java
```

**Main.java**

```java
import models.Ticket;
import models.Usuario;
import utils.InputHelper;

import java.util.ArrayList;
import java.util.List;

public class Main {

    private static final List<Ticket> tickets = new ArrayList<>();
    private static final List<Usuario> usuarios = new ArrayList<>();

    private static int nextTicketId = 1;
    private static int nextUserId = 1;

    public static void main(String[] args) {
        InputHelper in = new InputHelper();

        System.out.println("=== Sistema de Tickets (Java) ===");

        boolean running = true;
        while (running) {
            printMenu();

            int option = in.readIntInRange("Selecciona una opción: ", 1, 8);

            switch (option) {
                case 1 -> crearTicket(in);
                case 2 -> listarTickets();
                case 3 -> filtrarPorEstado(in);
                case 4 -> filtrarPorSeveridad(in);
                case 5 -> buscarPorId(in);
                case 6 -> cambiarEstado(in);
                case 7 -> mostrarMetricas();
                case 8 -> {
                    System.out.println("Saliendo... 👋");
                    running = false;
                }
            }
        }

        in.close();
    }

    private static void printMenu() {
        System.out.println("\n--- Menú ---");
        System.out.println("1) Crear ticket");
        System.out.println("2) Listar tickets");
        System.out.println("3) Filtrar por estado");
        System.out.println("4) Filtrar por severidad");
        System.out.println("5) Buscar por ID");
        System.out.println("6) Cambiar estado");
        System.out.println("7) Métricas");
        System.out.println("8) Salir");
    }

    private static void crearTicket(InputHelper in) {
        System.out.println("\n--- Crear ticket ---");

        String titulo = in.readNonEmptyString("Título: ");
        String descripcion = in.readNonEmptyString("Descripción: ");
        int sev = in.readIntInRange("Severidad (1-3): ", 1, 3);

        String nombreSolicitante = in.readNonEmptyString("Nombre solicitante: ");
        Usuario solicitante = findOrCreateUser(nombreSolicitante);

        Ticket ticket = new Ticket(
                nextTicketId++,
                titulo,
                descripcion,
                Ticket.Severity.fromInt(sev),
                Ticket.Status.OPEN,
                solicitante
        );

        tickets.add(ticket);
        System.out.println("Ticket creado: " + ticket.getSummary());
    }

    private static Usuario findOrCreateUser(String name) {
        for (Usuario u : usuarios) {
            if (u.getNombre().equalsIgnoreCase(name.trim())) {
                return u;
            }
        }
        Usuario nuevo = new Usuario(nextUserId++, name.trim());
        usuarios.add(nuevo);
        return nuevo;
    }

    private static void listarTickets() {
        System.out.println("\n--- Lista de tickets ---");
        if (tickets.isEmpty()) {
            System.out.println("No hay tickets registrados.");
            return;
        }
        for (Ticket t : tickets) {
            System.out.println(t.getSummary());
        }
    }

    private static void filtrarPorEstado(InputHelper in) {
        System.out.println("\n--- Filtrar por estado ---");
        Ticket.Status status = readStatus(in);
        boolean found = false;

        for (Ticket t : tickets) {
            if (t.getStatus() == status) {
                System.out.println(t.getSummary());
                found = true;
            }
        }

        if (!found) {
            System.out.println("No hay tickets con estado: " + status);
        }
    }

    private static void filtrarPorSeveridad(InputHelper in) {
        System.out.println("\n--- Filtrar por severidad ---");
        int sev = in.readIntInRange("Severidad (1-3): ", 1, 3);
        Ticket.Severity severity = Ticket.Severity.fromInt(sev);

        boolean found = false;
        for (Ticket t : tickets) {
            if (t.getSeverity() == severity) {
                System.out.println(t.getSummary());
                found = true;
            }
        }

        if (!found) {
            System.out.println("No hay tickets con severidad: " + severity);
        }
    }

    private static void buscarPorId(InputHelper in) {
        System.out.println("\n--- Buscar por ID ---");
        int id = in.readIntInRange("ID ticket: ", 1, Integer.MAX_VALUE);

        Ticket t = findTicketById(id);
        if (t == null) {
            System.out.println("No existe ticket con ID: " + id);
            return;
        }
        System.out.println(t.getDetails());
    }

    private static void cambiarEstado(InputHelper in) {
        System.out.println("\n--- Cambiar estado ---");
        int id = in.readIntInRange("ID ticket: ", 1, Integer.MAX_VALUE);

        Ticket t = findTicketById(id);
        if (t == null) {
            System.out.println("No existe ticket con ID: " + id);
            return;
        }

        System.out.println("Estado actual: " + t.getStatus());
        Ticket.Status newStatus = readStatus(in);

        try {
            t.changeStatus(newStatus);
            System.out.println("Estado actualizado: " + t.getSummary());
        } catch (IllegalStateException ex) {
            System.out.println("No se pudo cambiar el estado: " + ex.getMessage());
        }
    }

    private static Ticket findTicketById(int id) {
        for (Ticket t : tickets) {
            if (t.getId() == id) return t;
        }
        return null;
    }

    private static Ticket.Status readStatus(InputHelper in) {
        System.out.println("Estados disponibles: 1) OPEN  2) CLOSED");
        int choice = in.readIntInRange("Selecciona estado (1-2): ", 1, 2);
        return (choice == 1) ? Ticket.Status.OPEN : Ticket.Status.CLOSED;
    }

    private static void mostrarMetricas() {
        System.out.println("\n--- Métricas ---");
        if (tickets.isEmpty()) {
            System.out.println("No hay tickets para calcular métricas.");
            return;
        }

        int open = 0, closed = 0;
        int s1 = 0, s2 = 0, s3 = 0;

        for (Ticket t : tickets) {
            if (t.getStatus() == Ticket.Status.OPEN) open++;
            else closed++;

            switch (t.getSeverity()) {
                case S1 -> s1++;
                case S2 -> s2++;
                case S3 -> s3++;
            }
        }

        System.out.println("Total tickets: " + tickets.size());
        System.out.println("OPEN: " + open + " | CLOSED: " + closed);
        System.out.println("Severidad S1: " + s1 + " | S2: " + s2 + " | S3: " + s3);
    }
}
```

**models/Usuario.java**

```java
package models;

public class Usuario {
    private final int id;
    private final String nombre;

    public Usuario(int id, String nombre) {
        if (nombre == null || nombre.trim().isEmpty()) {
            throw new IllegalArgumentException("El nombre no puede ser vacío.");
        }
        this.id = id;
        this.nombre = nombre.trim();
    }

    public int getId() {
        return id;
    }

    public String getNombre() {
        return nombre;
    }

    @Override
    public String toString() {
        return nombre + " (#" + id + ")";
    }
}
```

**models/Ticket.java**

```java
package models;

import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

public class Ticket {
    public enum Status { OPEN, CLOSED }
    public enum Severity { S1, S2, S3;

        public static Severity fromInt(int v) {
            return switch (v) {
                case 1 -> S1;
                case 2 -> S2;
                case 3 -> S3;
                default -> throw new IllegalArgumentException("Severidad fuera de rango (1-3).");
            };
        }
    }

    private final int id;
    private final String titulo;
    private final String descripcion;
    private final Severity severity;
    private Status status;
    private final Usuario solicitante;
    private final LocalDateTime createdAt;

    public Ticket(int id,
                  String titulo,
                  String descripcion,
                  Severity severity,
                  Status status,
                  Usuario solicitante) {

        if (titulo == null || titulo.trim().isEmpty()) {
            throw new IllegalArgumentException("El título no puede ser vacío.");
        }
        if (descripcion == null || descripcion.trim().isEmpty()) {
            throw new IllegalArgumentException("La descripción no puede ser vacía.");
        }
        if (severity == null) {
            throw new IllegalArgumentException("Severidad obligatoria.");
        }
        if (status == null) {
            throw new IllegalArgumentException("Estado obligatorio.");
        }
        if (solicitante == null) {
            throw new IllegalArgumentException("Solicitante obligatorio.");
        }

        this.id = id;
        this.titulo = titulo.trim();
        this.descripcion = descripcion.trim();
        this.severity = severity;
        this.status = status;
        this.solicitante = solicitante;
        this.createdAt = LocalDateTime.now();
    }

    public int getId() {
        return id;
    }

    public Severity getSeverity() {
        return severity;
    }

    public Status getStatus() {
        return status;
    }

    public Usuario getSolicitante() {
        return solicitante;
    }

    public void changeStatus(Status newStatus) {
        if (newStatus == null) {
            throw new IllegalArgumentException("El nuevo estado no puede ser null.");
        }

        // Regla simple: si está CLOSED, no vuelve a OPEN (puedes ajustar según pauta)
        if (this.status == Status.CLOSED && newStatus == Status.OPEN) {
            throw new IllegalStateException("Un ticket CLOSED no puede volver a OPEN.");
        }

        // Regla simple: si ya está en el mismo estado, no hace nada (o lanza error)
        if (this.status == newStatus) {
            throw new IllegalStateException("El ticket ya está en estado " + newStatus + ".");
        }

        this.status = newStatus;
    }

    public String getSummary() {
        return String.format(
                "ID:%d | %s | Sev:%s | Estado:%s | Solicitante:%s",
                id, titulo, severity, status, solicitante.getNombre()
        );
    }

    public String getDetails() {
        DateTimeFormatter fmt = DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm");
        return "----- Ticket -----\n" +
                "ID: " + id + "\n" +
                "Título: " + titulo + "\n" +
                "Descripción: " + descripcion + "\n" +
                "Severidad: " + severity + "\n" +
                "Estado: " + status + "\n" +
                "Solicitante: " + solicitante + "\n" +
                "Creado: " + createdAt.format(fmt) + "\n";
    }
}

```

**utils/InputHelper.java**


```java
package utils;

import java.util.Scanner;

public class InputHelper {
    private final Scanner sc;

    public InputHelper() {
        this.sc = new Scanner(System.in);
    }

    public String readNonEmptyString(String prompt) {
        while (true) {
            System.out.print(prompt);
            String line = sc.nextLine();
            if (line != null && !line.trim().isEmpty()) {
                return line.trim();
            }
            System.out.println("Entrada inválida. No puede ser vacía.");
        }
    }

    public int readIntInRange(String prompt, int min, int max) {
        while (true) {
            int value = readInt(prompt);
            if (value >= min && value <= max) return value;
            System.out.println("Fuera de rango. Debe estar entre " + min + " y " + max + ".");
        }
    }

    public int readInt(String prompt) {
        while (true) {
            System.out.print(prompt);
            String line = sc.nextLine();
            try {
                return Integer.parseInt(line.trim());
            } catch (NumberFormatException e) {
                System.out.println("Entrada inválida. Debes ingresar un número entero.");
            }
        }
    }

    public boolean readYesNo(String prompt) {
        while (true) {
            System.out.print(prompt + " (S/N): ");
            String line = sc.nextLine().trim().toUpperCase();
            if (line.equals("S")) return true;
            if (line.equals("N")) return false;
            System.out.println("Respuesta inválida. Ingresa S o N.");
        }
    }

    public void close() {
        sc.close();
    }
}

```

**Cómo compilar y ejecutar (sin IDE)**

Desde la carpeta ProyectoTickets:



```bash
javac -d out src\Main.java src\models\*.java src\utils\*.java
java -cp out Main
```


**Cómo usar estas plantillas en evaluaciones (recomendación práctica)**

E3: entregas Main.java simplificado + 3 archivos Ej1.java, etc. (plantilla con TODOs).

E4: entregas Usuario y Ticket ya creados (o parcialmente) + Main con menú base, y ellos completan reglas + flujo.

C2/Examen: entregas solo estructura de carpetas (vacía o con stubs) y el enunciado exige robustez + pruebas.
