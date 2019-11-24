# Ejemplo-Repositorio
package Modelo;

import com.sun.org.apache.xerces.internal.impl.xpath.regex.Match;
import java.util.ArrayList;
import javax.swing.JOptionPane;
import java.lang.Math;

public class Todo {

    private String operando;
    private String codOperacion;
    private String dirOperando;
    private String registro;
    private String acumulador;
    private String modDireccion;
    private ArrayList<Memoria> Memoria;
    private ArrayList<Registro> Registros;

    public Todo() {
        Memoria = new ArrayList<>();
        Registros = new ArrayList<>();
        for (int i = 0; i < 20; i++) {
            Memoria m = new Memoria();
            m.setDato(Integer.toString(numRandom()));
            m.setPMemoria(Integer.toString(i));

            Memoria.add(m);
        }

        for (int i = 0; i < 10; i++) {
            Registro m = new Registro();
            m.setDato(Integer.toString(numRandomR()));
            m.setNumeroRegistro(Integer.toString(i));

            Registros.add(m);
        }

    }

    public Todo(String operando, String codOperacion, String dirOperando, String registro, String acumulador, String modDireccion) {
        this.operando = operando;
        this.codOperacion = codOperacion;
        this.dirOperando = dirOperando;
        this.registro = registro;
        this.acumulador = acumulador;
        this.modDireccion = modDireccion;

    }

    public String Inmediato(String Operando, String Ac, String Condicion) {

        String Resultado = "";

        switch (Condicion) {
            case "SUMA":
                Resultado = Integer.toString(Integer.parseInt(Operando) + Integer.parseInt(Ac));
                break;
            case "RESTA":
                Resultado = Integer.toString(Integer.parseInt(Operando) - Integer.parseInt(Ac));
                break;
            case "MULTIPLICACION":
                Resultado = Integer.toString(Integer.parseInt(Operando) * Integer.parseInt(Ac));
                break;
            case "DIVISION":
                Resultado = Double.toString(Double.parseDouble(Operando) / Double.parseDouble(Ac));
                break;
            case "POTENCIA":
                Resultado = Double.toString(Math.pow(Integer.parseInt(Operando), Integer.parseInt(Ac)));
                break;
            case "LOGARITMO":
                Resultado = Double.toString(Math.log(Double.parseDouble(Operando)) / Math.log(Double.parseDouble(Ac)));
                break;
            case "RADICACION":
                Resultado = Double.toString(Math.pow(Double.parseDouble(Operando), 1 / Double.parseDouble(Ac)));
                break;
        }

        return Resultado;
    }

    public String Directo(String Operando, String Ac, String Condicion) {

        String Resultado = "";
        String RBusqueda = "";

        for (int i = 0; i < Memoria.size(); i++) {

            if (Memoria.get(i).getPMemoria().equals(Operando)) {

                RBusqueda = Memoria.get(i).getDato();
            }
        }

        switch (Condicion) {
            case "SUMA":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda) + Integer.parseInt(Ac));
                break;
            case "RESTA":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda) - Integer.parseInt(Ac));
                break;
            case "MULTIPLICACION":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda) * Integer.parseInt(Ac));
                break;
            case "DIVISION":
                Resultado = Double.toString(Double.parseDouble(RBusqueda) / Double.parseDouble(Ac));
                break;
            case "POTENCIA":
                Resultado = Double.toString(Math.pow(Integer.parseInt(RBusqueda), Integer.parseInt(Ac)));
                break;
            case "LOGARITMO":
                Resultado = Double.toString(Math.log(Double.parseDouble(RBusqueda)) / Math.log(Double.parseDouble(Ac)));
                break;
            case "RADICACION":
                Resultado = Double.toString(Math.pow(Double.parseDouble(RBusqueda), 1 / Double.parseDouble(Ac)));
                break;
        }

        return Resultado;
    }

    public String Indirecto(String Operando, String Ac, String Condicion) {

        String Resultado = "";
        String RBusqueda = "";
        String RBusqueda2 = "";

        for (int i = 0; i < Memoria.size(); i++) {

            if (Memoria.get(i).getPMemoria().equals(Operando)) {

                RBusqueda = Memoria.get(i).getDato();

            }
        }

        for (int i = 0; i < Memoria.size(); i++) {

            if (Memoria.get(i).getPMemoria().equals(RBusqueda)) {

                RBusqueda2 = Memoria.get(i).getDato();
            }
        }

        switch (Condicion) {
            case "SUMA":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda2) + Integer.parseInt(Ac));
                break;
            case "RESTA":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda2) - Integer.parseInt(Ac));
                break;
            case "MULTIPLICACION":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda2) * Integer.parseInt(Ac));
                break;
            case "DIVISION":
                Resultado = Double.toString(Double.parseDouble(RBusqueda2) / Double.parseDouble(Ac));
                break;
            case "POTENCIA":
                Resultado = Double.toString(Math.pow(Integer.parseInt(RBusqueda2), Integer.parseInt(Ac)));
                break;
            case "LOGARITMO":
                Resultado = Double.toString(Math.log(Double.parseDouble(RBusqueda2)) / Math.log(Double.parseDouble(Ac)));
                break;
            case "RADICACION":
                Resultado = Double.toString(Math.pow(Double.parseDouble(RBusqueda2), 1 / Double.parseDouble(Ac)));
                break;

        }

        return Resultado;
    }

    public String Registro(String Registro, String Ac, String Condicion) {

        String Resultado = "";
        String RBusqueda = "";

        for (int i = 0; i < Registros.size(); i++) {

            if (Registros.get(i).getNumeroRegistro().equals(Registro)) {

                RBusqueda = Registros.get(i).getDato();
            }
        }

        switch (Condicion) {

            case "SUMA":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda) + Integer.parseInt(Ac));
                break;
            case "RESTA":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda) - Integer.parseInt(Ac));
                break;
            case "MULTIPLICACION":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda) * Integer.parseInt(Ac));
                break;
            case "DIVISION":
                Resultado = Double.toString(Double.parseDouble(RBusqueda) / Double.parseDouble(Ac));
                break;
            case "POTENCIA":
                Resultado = Double.toString(Math.pow(Integer.parseInt(RBusqueda), Integer.parseInt(Ac)));
                break;
            case "LOGARITMO":
                Resultado = Double.toString(Math.log(Double.parseDouble(RBusqueda)) / Math.log(Double.parseDouble(Ac)));
                break;
            case "RADICACION":
                Resultado = Double.toString(Math.pow(Double.parseDouble(RBusqueda), 1 / Double.parseDouble(Ac)));
                break;
        }
        return Resultado;
    }

    public String IndirectoRegistro(String Registro, String Ac, String Condicion) {

        String Resultado = "";
        String RBusqueda = "";
        String RBusqueda2 = "";

        for (int i = 0; i < Registros.size(); i++) {

            if (Registros.get(i).getNumeroRegistro().equals(Registro)) {

                RBusqueda = Registros.get(i).getDato();
            }
        }
        for (int i = 0; i < Memoria.size(); i++) {

            if (Memoria.get(i).getPMemoria().equals(RBusqueda)) {

                RBusqueda2 = Memoria.get(i).getDato();
            }
        }

        switch (Condicion) {

            case "SUMA":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda2) + Integer.parseInt(Ac));
                break;
            case "RESTA":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda2) - Integer.parseInt(Ac));
                break;
            case "MULTIPLICACION":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda2) * Integer.parseInt(Ac));
                break;
            case "DIVISION":
                Resultado = Double.toString(Double.parseDouble(RBusqueda2) / Double.parseDouble(Ac));
                break;
            case "POTENCIA":
                Resultado = Double.toString(Math.pow(Integer.parseInt(RBusqueda2), Integer.parseInt(Ac)));
                break;
            case "LOGARITMO":
                Resultado = Double.toString(Math.log(Double.parseDouble(RBusqueda2)) / Math.log(Double.parseDouble(Ac)));
                break;
            case "RADICACION":
                Resultado = Double.toString(Math.pow(Double.parseDouble(RBusqueda2), 1 / Double.parseDouble(Ac)));
                break;
        }
        return Resultado;
    }

    public String Desplazamiento(String Registro, String Operando, String Ac, String Condicion) {

        String Resultado = "";
        String RBusqueda = "";
        String RBusqueda2 = "";

        for (int i = 0; i < Registros.size(); i++) {

            if (Registros.get(i).getNumeroRegistro().equals(Registro)) {

                RBusqueda = Registros.get(i).getDato();

            }
        }
        RBusqueda = Integer.toString(Integer.parseInt(RBusqueda) + Integer.parseInt(Operando));

        for (int i = 0; i < Memoria.size(); i++) {

            if (Memoria.get(i).getPMemoria().equals(RBusqueda)) {

                RBusqueda2 = Memoria.get(i).getDato();
            }
        }

        switch (Condicion) {

            case "SUMA":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda2) + Integer.parseInt(Ac));
                break;
            case "RESTA":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda2) - Integer.parseInt(Ac));
                break;
            case "MULTIPLICACION":
                Resultado = Integer.toString(Integer.parseInt(RBusqueda2) * Integer.parseInt(Ac));
                break;
            case "DIVISION":
                Resultado = Double.toString(Double.parseDouble(RBusqueda2) / Double.parseDouble(Ac));
                break;
            case "POTENCIA":
                Resultado = Double.toString(Math.pow(Integer.parseInt(RBusqueda2), Integer.parseInt(Ac)));
                break;
            case "LOGARITMO":
                Resultado = Double.toString(Math.log(Double.parseDouble(RBusqueda2)) / Math.log(Double.parseDouble(Ac)));
                break;
            case "RADICACION":
                Resultado = Double.toString(Math.pow(Double.parseDouble(RBusqueda2), 1 / Double.parseDouble(Ac)));
                break;
        }

        return Resultado;
    }

    public String getOperando() {
        return operando;
    }

    public void setOperando(String operando) {
        this.operando = operando;
    }

    public String getCodOperacion() {
        return codOperacion;
    }

    public void setCodOperacion(String codOperacion) {
        this.codOperacion = codOperacion;
    }

    public String getDirOperando() {
        return dirOperando;
    }

    public void setDirOperando(String dirOperando) {
        this.dirOperando = dirOperando;
    }

    public String getRegistro() {
        return registro;
    }

    public void setRegistro(String registro) {
        this.registro = registro;
    }

    public String getAcumulador() {
        return acumulador;
    }

    public void setAcumulador(String acumulador) {
        this.acumulador = acumulador;
    }

    public String getModDireccion() {
        return modDireccion;
    }

    public void setModDireccion(String modDireccion) {
        this.modDireccion = modDireccion;
    }

    public int numRandom() {
        int n = (int) (Math.random() * 19) + 1;
        return n;
    }

    public int numRandomR() {
        int n = (int) (Math.random() * 15);
        return n;
    }

    public ArrayList<Memoria> getMemoria() {
        return Memoria;
    }

    public void setMemoria(ArrayList<Memoria> Memoria) {
        this.Memoria = Memoria;
    }

    public ArrayList<Registro> getRegistros() {
        return Registros;
    }

    public void setRegistros(ArrayList<Registro> Registros) {
        this.Registros = Registros;
    }

}
