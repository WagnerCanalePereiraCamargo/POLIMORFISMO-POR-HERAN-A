# O código proposto adota uma abordagem eficaz ao utilizar o conceito de polimorfismo por herança para modelar diferentes tipos de animais. Essa escolha apresenta diversas vantagens, destacando-se pela simplicidade, clareza e facilidade de manutenção.

Em termos de **simplicidade e clareza**, o código se beneficia da estrutura hierárquica, onde cada classe de animal herda características comuns da classe base `Animal`. Essa relação de herança reflete de maneira intuitiva a hierarquia natural entre os animais, tornando o código mais fácil de entender para outros desenvolvedores.

A **reusabilidade de código** é evidente na implementação dos métodos `fazerSom()` e `comer()`. A lógica comum é centralizada na classe base `Animal`, proporcionando uma base sólida para cada classe derivada. Isso não apenas simplifica o desenvolvimento de novos tipos de animais, mas também facilita a manutenção, pois alterações na lógica comum podem ser feitas em um único local.

A **facilidade de extensão** é uma característica marcante do código. Adicionar novos tipos de animais é um processo direto: basta criar uma nova classe derivada de `Animal` e implementar os métodos específicos. A estrutura do código permite a incorporação contínua de novas entidades sem afetar a lógica existente.

A **manutenção simplificada** é um resultado direto da abordagem adotada. Modificações na forma como todos os animais emitem som ou se alimentam podem ser realizadas na classe base `Animal`. Essas alterações serão automaticamente refletidas em todas as classes derivadas, proporcionando coesão e evitando redundâncias.

A **escalabilidade** do código é notável à medida que novos tipos de animais são introduzidos. A hierarquia de herança oferece uma estrutura flexível que facilita o gerenciamento e a expansão do sistema ao longo do tempo.

A implementação do **polimorfismo para tratamento uniforme** é evidenciada pela utilização de uma lista de animais (`List<Animal> animais`). O loop de impressão percorre essa lista, chamando os métodos `fazerSom()` e `comer()` para cada animal. Isso destaca a capacidade de tratar objetos de classes diferentes de maneira uniforme, aproveitando a polimorfia oferecida pela herança.

Em resumo, o código se destaca pela sua elegância e eficiência ao aplicar princípios fundamentais da programação orientada a objetos. A abordagem de polimorfismo por herança proporciona um design intuitivo, fácil de entender e manter, além de ser altamente flexível para a incorporação de novas entidades ao sistema.



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
