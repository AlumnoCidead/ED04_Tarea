# ED04_Tarea
Creación de un repositorio público en el que poder llevar a cabo los ejercicios relacionados con GIT para la asignatura de Entornos de Desarrollo.


package cuentas;
/**
 * 
 * @author Sandra Macías Aragón
 * @version 6/02/2023
 */
public class Main {
/**
 * método principal de la clase Main
 * @param args 
 */
    public static void main(String[] args) {
    
        CCuenta cuenta1;
        double saldoActual;

        operativa_cuenta(0);
    }
    /**
     * método que realiza operaciones con el contenido de la cuenta
     * @param cantidad 
     */
    public static void operativa_cuenta(float cantidad) {
        
        CCuenta cuenta1;
        double saldoActual;
        cuenta1 = new CCuenta("Antonio LÃ³pez", "1000-2365-85-1230456789", 2500, 0);
        saldoActual = cuenta1.estado();
        System.out.println("El saldo actual es" + saldoActual);
        try {
            cuenta1.retirar(2300);
        } catch (Exception e) {
            System.out.print("Fallo al retirar");
        }
        try {
            System.out.println("Ingreso en cuenta");
            cuenta1.ingresar(695);
        } catch (Exception e) {
            System.out.print("Fallo al ingresar");
        }
    }
}


public class CCuenta {

    /**método que devuelve nombre
     * @return nombre
     */
    public String getNombre() {
        return nombre;
    }

    /**
     * método que establece un valor para nombre
     * @param nombre 
     */
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    /**
     * método que devuelve una cuenta
     * @return cuenta
     */
    public String getCuenta() {
        return cuenta;
    }

    /**
     * método que establece un valor para cuenta
     * @param cuenta
     */
    public void setCuenta(String cuenta) {
        this.cuenta = cuenta;
    }

    /**
     * método que devuelve saldo
     * @return saldo
     */
    public double getSaldo() {
        return saldo;
    }

    /**
     * método que establece un valor para saldo
     * @param saldo 
     */
    public void setSaldo(double saldo) {
        this.saldo = saldo;
    }

    /**
     * método que devuelve tipo de interes
     * @return tipoInteres
     */
    public double getTipoInteres() {
        return tipoInteres;
    }

    /**
     * método que establece un valor para tipoInteres
     * @param tipoInteres the tipoInteres to set
     */
    public void setTipoInteres(double tipoInteres) {
        this.tipoInteres = tipoInteres;
    }
    
    private String nombre;
    private String cuenta;
    private double saldo;
    private double tipoInteres;
  
    public CCuenta() {
    }
    /**
     * Constructor de la clase CCuenta
     * @param nom
     * @param cue
     * @param sal
     * @param tipo 
     */
    public CCuenta(String nom, String cue, double sal, double tipo) {
        nombre = nom;
        cuenta = cue;
        saldo = sal;
    }
    /**
     * método que pregunta por el estado de la cuenta
     * @return getSaldo
     */
    public double estado() {
        return getSaldo();
    }
    /**
     * método para ingresar cantidad determinada de saldo
     * @param cantidad
     * @throws Exception 
     */
    public void ingresar(double cantidad) throws Exception {
        if (cantidad < 0) {
            throw new Exception("No se puede ingresar una cantidad negativa");
        }
        setSaldo(getSaldo() + cantidad);
    }
    /**
     * método para retirar cantidad determinada de saldo
     * @param cantidad
     * @throws Exception 
     */
    public void retirar(double cantidad) throws Exception {
        if (cantidad <= 0) {
            throw new Exception("No se puede retirar una cantidad negativa");
        }
        if (estado() < cantidad) {
            throw new Exception("No se hay suficiente saldo");
        }
        setSaldo(getSaldo() - cantidad);
    }
    
}
