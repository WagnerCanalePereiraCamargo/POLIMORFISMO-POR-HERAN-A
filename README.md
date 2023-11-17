# POLIMORFISMO-POR-HERAN-A

import java.util.ArrayList;
import java.util.List;

// Classe base Animal
abstract class Animal {
    abstract void fazerSom();
    abstract void comer();
}

// Cachorro herda de Animal
class Cachorro extends Animal {
    @Override
    void fazerSom() {
        System.out.println("Au au!");
    }

    @Override
    void comer() {
        System.out.println("Cachorro comendo ração.");
    }
}

// Gato herda de Animal
class Gato extends Animal {
    @Override
    void fazerSom() {
        System.out.println("Miau!");
    }

    @Override
    void comer() {
        System.out.println("Gato comendo peixe.");
    }
}

// Papagaio herda de Animal
class Papagaio extends Animal {
    @Override
    void fazerSom() {
        System.out.println("Loro!!!");
    }

    @Override
    void comer() {
        System.out.println("Papagaio comendo sementes.");
    }
}

// Teste de polimorfismo por herança
public class TestePolimorfismo {
    public static void main(String[] args) {
        List<Animal> animais = new ArrayList<>();

        Cachorro cachorro = new Cachorro();
        Gato gato = new Gato();
        Papagaio papagaio = new Papagaio();

        animais.add(cachorro);
        animais.add(gato);
        animais.add(papagaio);

        System.out.println("Emitindo sons e alimentando:");
        for (Animal animal : animais) {
            animal.fazerSom();
            animal.comer();
            System.out.println("------------------------");
        }
    }
}
