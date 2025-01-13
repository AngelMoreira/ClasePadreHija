# ClasePadreHija
// Clase Padre
class Vehiculo {
    // Atributos de la clase padre
    String marca;
    String modelo;
    int año;
    double precio;

    // Constructor de la clase padre
    public Vehiculo(String marca, String modelo, int anio, double precio) {
        this.marca = marca;
        this.modelo = modelo;
        this.año = año;
        this.precio = precio;
    }

    // Métodos de la clase padre
    public void mostrarInformacion() {
        System.out.println("Marca: " + marca);
        System.out.println("Modelo: " + modelo);
        System.out.println("Año: " + anio);
        System.out.println("Precio: $" + precio);
    }

    public void encender() {
        System.out.println("El vehículo está encendido.");
    }
}

// Clase Hija 1
class Automovil extends Vehiculo {
    // Atributos adicionales
    private int numeroPuertas;
    private boolean tieneAireAcondicionado;
    private String tipoCombustible;

    // Constructor de la clase hija
    public Automovil(String marca, String modelo, int anio, double precio, int numeroPuertas, boolean tieneAireAcondicionado, String tipoCombustible) {
        super(marca, modelo, anio, precio); 
        this.numeroPuertas = numeroPuertas;
        this.tieneAireAcondicionado = tieneAireAcondicionado;
        this.tipoCombustible = tipoCombustible;
    }

    // Método adicional
    public void tocarBocina() {
        System.out.println("¡Bip bip! El automóvil está tocando la bocina.");
    }

    @Override
    public void mostrarInformacion() {
        super.mostrarInformacion(); 
        System.out.println("Número de puertas: " + numeroPuertas);
        System.out.println("Aire acondicionado: " + (tieneAireAcondicionado ? "Sí" : "No"));
        System.out.println("Tipo de combustible: " + tipoCombustible);
    }
}

// Clase Hija 2
class Motocicleta extends Vehiculo {
    // Atributos adicionales
    private String tipoMotocicleta;
    private int cilindrada;
    private boolean tieneMaletero;

    // Constructor de la clase hija
    public Motocicleta(String marca, String modelo, int anio, double precio, String tipoMotocicleta, int cilindrada, boolean tieneMaletero) {
        super(marca, modelo, anio, precio); 
        this.tipoMotocicleta = tipoMotocicleta;
        this.cilindrada = cilindrada;
        this.tieneMaletero = tieneMaletero;
    }

    // Método adicional
    public void hacerCaballito() {
        System.out.println("¡La motocicleta está haciendo un caballito!");
    }

    @Override
    public void mostrarInformacion() {
        super.mostrarInformacion(); 
        System.out.println("Tipo de motocicleta: " + tipoMotocicleta);
        System.out.println("Cilindrada: " + cilindrada + " cc");
        System.out.println("Tiene maletero: " + (tieneMaletero ? "Sí" : "No"));
    }
}

// Clase principal para probar
public class HerenciaVehiculos {
    public static void main(String[] args) {
        // Crear un objeto Automovil
        Automovil auto = new Automovil("Toyota", "Corolla", 2023, 25000.0, 4, true, "Gasolina");
        System.out.println("Información del Automóvil:");
        auto.mostrarInformacion();
        auto.tocarBocina();
        auto.encender();

        System.out.println("\n-\n");

        // Crear un objeto Motocicleta
        Motocicleta moto = new Motocicleta("Honda", "CBR600RR", 2022, 12000.0, "Deportiva", 600, false);
        System.out.println("Información de la Motocicleta:");
        moto.mostrarInformacion();
        moto.hacerCaballito();
        moto.encender();
    }
}
