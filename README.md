
# POO
## Ejercicio1: Tus expectativas antes de aprender POO. Qué creías que ibas a aprender y para qué creías que iba a servir lo que ibas a ver sobre este tema

### *Espectativas*:

1. **Desarrollar programas** simples que involucren diferentes objetos
1. Aprender a definir, evolucionar y comprender las **variables** que envulven a los objetos
1. Capacidad para trabajar con **interfaces** que relacionen al usuario con la aplicación

### *USOS*

|      Espectativas      | Uso                                                                             |
|:----------------------:|:--------------------------------------------------------------------------------|
| Desarrollar programas  | Formar una estructura y saber desenvolverla en pasos                            |
|       Variables        | Modificar valores de estas mismas así como conoces su funcionamiento individual |
|       Interfaces       | Facilitar al usuario el manejo de la aplicación                                 |

## Ejercicio2: Qué has aprendido durante las dos unidades
### **_LISTA_**

1. He aprendido a **crear estructuras** que engloben varios objetos diferentes y relacionarlos
1. Trabajar con propiedades,métodos y constructores
   * crear
   * evolucionar y variar
   *  llamar a otras _propiedades,métodos y constructores_
   * **características** de propiedades públicas privadas protegidas o amigables 
1. Relaciones entre objetos (agregación, asociación ...)
1. Comprender el funcionamiento de herencia de una clase a otra y como sobreponer métodos

![Imagen de POO](https://codersfree.nyc3.cdn.digitaloceanspaces.com/posts/que-es-el-lenguaje-de-programacion-orientada-a-objetos-poo.jpg)

---
Autor : Víctor Gutiérrez
Ejercicio: 3 POO GitMind
---

## Ejercicio3: Elige dos ejercicios de las prácticas que te hayan sido, para ti, los más importantes. Indica por qué y explica cómo lo has resuelto u lo que has aprendido con ellos
### **_~~Lizta~~ Lista de Ejercicios_**

|        Ejercicios        |                                       Motivo                                        | Aprendizaje                                                                                                                                                                                        |
|:------------------------:|:-----------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ordenadores y Servidores |       Presenta un caso real y práctico sobre programación orientada a objetos       | Me ha ayudado mucho a comprender como efectuar cada tipo de relación                                                                                                                               |
|    Password-Artículo     | Es otro tipo de caso real y útil para entender en profundidad métodos y propiedades | Gracias a este ejercicio he mejorado mi programación acerca de constructores, métodos y propiedades, también he podido aplicar programación previa para cumplir con los requisitos de la actividad |

![Contraseña](https://www.solutions4it.co.uk/wp-content/uploads/2023/08/password-attacks-1080x675.jpg.webp)

---
Fecha: 20/02/2024
---

## Ejercicio4: Explica tus conclusiones en este momento sobre estas dos unidades: Qué has aprendido realmente, qué utilidad le ves y di lo más positivo que has adquirido en estas dos unidades y lo que menos te ha gustado.
### 

1. ¿Qué has aprendido realmente?
   - [x]  Trabajar con objetos y definirlas correctamente
   - [x] Relacionar objetos entre sí
2. ¿Qué utilidades identifico?
   - [x] Poder simplificar el código reutilizándolo
   - [x] Me simplifica mucho el manejo de código
3. ¿Qué cosas positivas he adquirido?
   - [x] Acercarme a posibles ejemplos prácticos que me ayudan a obtener experiencia
   - [x] Una gran amplitud de usos y variaciones en el mundo de la programación


>Realizado por Víctor Gutiérrez López
>>Estudiante de DAM en el Juan De Herrera

## Ejercicio5: Presenta un ejemplo de códido de POO con algunas características que presente

* Ejemplo de la contraseña:
   - [x] Sencillo y claro
   - [x] Coherente
   - [x] Reutilizable
   - [ ] Código duplicado
````
  public class Password {
    private String password;
    private static final int MIN_LENGTH = 12;


    public Password(int tamaño){
        this.setPassword(tamaño);
    }

    public Password(){
        this.setPassword(12);
    }

    public Password(String password) {
        setPassword(password);
    }

    public void setPassword(int tamaño){
        char[] aux;

        if(tamaño < MIN_LENGTH){
            tamaño = MIN_LENGTH;
        }

        aux = new char[tamaño];

        int eleccion=1; //controla que toca ahora generar
        //1, Mayus, 2, Minus, 3, Num, 4, Simbolo
        this.password = "";
        for(int i = 0; i < tamaño; i++){
            eleccion = (eleccion == 4? 1:eleccion+1);
            switch (eleccion){
                case 1:
                    aux[i] = Password.mayúsculaAleatoria();
                    break;
                case 2:
                    aux[i] += Password.minúsculaAleatoria();
                    break;
                case 3:
                    aux[i] += Password.cifraAleatoria();
                    break;
                case 4:
                    aux[i] += Password.símboloAleatorio();
                    break;
            }
        }

        //shuffle de texto para revolver los caracteres
        for(int i = 0; i < 10* aux.length; i++){
            int pos1 = (int)(Math.random() * aux.length);
            int pos2 = (int)(Math.random() * aux.length);
            char temp = aux[pos1];
            aux[pos1] = aux[pos2];
            aux[pos2] = temp;
        }

        this.password = new String(aux);

    }

    public void setPassword(){
        this.setPassword(12);
    }

    public void setPassword(String password) {
        this.password = password;
    }

    public String getPassword() {
        return password;
    }

    public static char mayúsculaAleatoria(){
        return (char) (Math.random() * ('Z' - 'A') + 'A');
    }
    public static char minúsculaAleatoria(){
        return (char) (Math.random() * ('z' - 'a') + 'a');
    }
    public static char cifraAleatoria(){
        return (char)(Math.random() * 9 + '0');
    }

    public static char símboloAleatorio(){
        return (char) (Math.random() * (47 - 33) + 33);
    }


    public boolean esFuerte(){
        boolean mayus = password.matches(".*[A-Z].*");
        boolean minus = password.matches(".*[a-z].*");
        boolean simb = password.matches(".*[^a-zA-Z0-9].*");
        boolean num = password.matches(".*[0-9].*");
        boolean tam = (password.length() >= MIN_LENGTH);
        return mayus && minus && simb && num && tam;
    }
}
````
[Mi perfil de GitHub](https://github.com/VictorGL03)

