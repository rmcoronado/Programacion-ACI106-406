DIAGRAMA DE FLUJO – CÁTEDRA 1 (C1) – Sistema de Tickets (Python)

┌──────────────────────────────┐
│            INICIO            │
└───────────────┬──────────────┘
                │
                v
┌──────────────────────────────┐
│ Inicializar almacenamiento     │
│  - tickets = []               │
│  - next_id = 1                │
└───────────────┬──────────────┘
                │
                v
┌──────────────────────────────┐
│        BUCLE DEL MENÚ         │   (repetir hasta salir)
└───────────────┬──────────────┘
                │
                v
┌──────────────────────────────┐
│ Mostrar menú (1..5)           │
│ Leer opción con validación:   │
│  - entero                     │
│  - rango 1..5                 │
└───────────────┬──────────────┘
                │
                v
┌──────────────────────────────┐
│ ¿Opción = 5? (Salir)          │
└───────────┬───────────┬──────┘
            │ Sí        │ No
            v           v
┌───────────────────┐   ┌──────────────────────────────┐
│ Imprimir           │   │ Ejecutar opción 1/2/3/4       │
│ "Saliendo..."      │   │ y luego volver al menú        │
│ FIN                │   └───────────────┬──────────────┘
└───────────────────┘                   │
                                        v
                          ┌──────────────────────────────┐
                          │ ¿Qué opción?                  │
                          └───────┬─────────┬────────────┘
                                  │         │
                    ┌─────────────┘         └─────────────┐
                    v                                     v

Opción 1: CREAR TICKET                         Opción 2: LISTAR TICKETS
──────────────────────                         ─────────────────────────
- Leer título (no vacío)                       - Si tickets está vacío:
- Leer severidad (1..3)                          informar "No hay tickets"
- Leer estado (abierto/cerrado)                - Si hay tickets:
- Crear ticket:                                  imprimir cada ticket
  {id: next_id, titulo, severidad, estado}        en formato claro
- tickets.append(ticket)
- next_id += 1

                    ┌─────────────┐         ┌─────────────┐
                    v             │         │             v

Opción 3: BUSCAR POR ID                        Opción 4: CERRAR TICKET POR ID
──────────────────────                        ─────────────────────────────
- Leer ID (entero positivo)                    - Leer ID (entero positivo)
- Buscar en tickets                            - Buscar ticket en tickets
  - Si no existe: informar                       - Si no existe: informar
  - Si existe: imprimir ticket                   - Si ya cerrado: informar
                                                 - Si abierto: estado="cerrado"
                                                   e imprimir confirmación

                    ┌─────────────────────────────────────────┐
                    │ Volver al BUCLE DEL MENÚ (repetir)       │
                    └─────────────────────────────────────────┘
