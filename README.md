# L_04_Z1
import java.util.Arrays;
import java.util.Objects;


class Гітара {
   private Струна[] струни;
   private Корпус корпус;


   public Гітара(int кількістьСтрун, Корпус корпус) {
       струни = new Струна[кількістьСтрун];
       this.корпус = корпус;
       for (int i = 0; i < кількістьСтрун; i++) {
           струни[i] = new Струна();
       }
   }


   public void грати() {
       System.out.println("Граємо на гітарі");
   }


   public void налаштовувати() {
       System.out.println("Налаштовуємо гітару");
   }


   public void замінитиСтруну(int номерСтруни) {
       if (номерСтруни >= 0 && номерСтруни < струни.length)
       {
           струни[номерСтруни] = new Струна();
           System.out.println("Замінено струну номер " + номерСтруни);
       } else {
           System.out.println("Некоректний номер струни");
       }
   }


   @Override
   public boolean equals(Object obj) {
       if (this == obj) return true;
       if (obj == null || getClass() != obj.getClass()) return false;
       Гітара гітара = (Гітара) obj;
       return Arrays.equals(струни, гітара.струни) && Objects.equals(корпус, гітара.корпус);
   }


   @Override
   public int hashCode() {
       int result = Objects.hash(корпус);
       result = 31 * result + Arrays.hashCode(струни);
       return result;
   }


   @Override
   public String toString() {
       return "Гітара{" +
               "струни=" + Arrays.toString(струни) +
               ", корпус=" + корпус +
               '}';
   }
}


class Струна {


   @Override
   public boolean equals(Object obj) {
       if (this == obj) return true;
       if (obj == null || getClass() != obj.getClass()) return false;
       // Додає логіку порівняння для струни
       return true;
   }


   @Override
   public int hashCode() {
       // Додає логіку обчислення hashCode для струни
       return 0;
   }


   @Override
   public String toString() {
       // Повертає рядок, який описує струну
       return "Струна";
   }
}


class Корпус {


   @Override
   public boolean equals(Object obj) {
       if (this == obj) return true;
       if (obj == null || getClass() != obj.getClass()) return false;
       // Додання логіки порівняння для корпусу
       return true;
   }


   @Override
   public int hashCode() {
       // Додання логіки обчислення hashCode для корпусу
       return 0;
   }


   @Override
   public String toString() {
       // Повернення рядка, який описує корпус
       return "Корпус";
   }
}
public class Main {
   public static void main(String[] args) {
       Гітара гітара = new Гітара(6, new Корпус());


       гітара.грати();
       гітара.налаштовувати();
       гітара.замінитиСтруну(2);


       System.out.println(гітара);
   }
}
