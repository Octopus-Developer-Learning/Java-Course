# Curso Completo de Java: Básico, Intermediário e Avançado

## Objetivo
Ensinar Java de forma abrangente, cobrindo desde conceitos básicos até tópicos avançados, com foco em desenvolvimento profissional. Este curso é ideal para quem deseja dominar Java para aplicações reais.

## Nível 1: Básico

### Módulo 1: Fundamentos de Java
- **História e características do Java**.
- **Estrutura de um programa Java**:
  - Classes, métodos, `main`.
- **Exemplo**:

```java
public class PrimeiroPrograma {
    public static void main(String[] args) {
        System.out.println("Meu primeiro programa em Java!");
    }
}
```

- **Exercício 1**: Crie um programa que exiba a data atual.

### Módulo 2: Estruturas de Controle e Dados
- **Variáveis e tipos de dados**:
  - `int`, `double`, `char`, `String`, `boolean`.
- **Condicionais e laços**:
  - `if`, `switch`, `for`, `while`.
- **Exemplo**:

```java
public class AnoBissexto {
    public static void main(String[] args) {
        int ano = 2024;
        if ((ano % 4 == 0 && ano % 100 != 0) || (ano % 400 == 0)) {
            System.out.println(ano + " é bissexto");
        } else {
            System.out.println(ano + " não é bissexto");
        }
    }
}
```

- **Exercício 2**: Crie um programa que determine se um ano é bissexto.

### Módulo 3: Métodos e Modularização
- Criando métodos com e sem retorno.
- Sobrecarga de métodos.
- **Exemplo**:

```java
public class Calculadora {
    public static int somar(int a, int b) {
        return a + b;
    }

    public static double somar(double a, double b) {
        return a + b;
    }

    public static void main(String[] args) {
        System.out.println("Soma inteiros: " + somar(5, 3));
        System.out.println("Soma doubles: " + somar(5.5, 3.3));
    }
}
```

- **Exercício 3**: Crie métodos sobrecarregados para calcular a área de um círculo e de um retângulo.

## Nível 2: Intermediário

### Módulo 1: Programação Orientada a Objetos (POO)
- **Conceitos**:
  - Classes, objetos, encapsulamento, herança, polimorfismo.
- **Exemplo**:

```java
public class Pessoa {
    private String nome;
    private int idade;

    public Pessoa(String nome, int idade) {
        this.nome = nome;
        this.idade = idade;
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }
}

public class Main {
    public static void main(String[] args) {
        Pessoa p = new Pessoa("Maria", 30);
        System.out.println("Nome: " + p.getNome());
    }
}
```

- **Exercício 1**: Crie uma classe `Carro` com atributos `marca`, `modelo` e métodos para acelerar e frear.

### Módulo 2: Coleções
- **Listas** (`ArrayList`), **Conjuntos** (`HashSet`), **Mapas** (`HashMap`).
- **Exemplo**:

```java
import java.util.ArrayList;

public class ListaExemplo {
    public static void main(String[] args) {
        ArrayList<String> nomes = new ArrayList<>();
        nomes.add("Ana");
        nomes.add("Bruno");
        for (String nome : nomes) {
            System.out.println(nome);
        }
    }
}
```

- **Exercício 2**: Crie um programa que gerencie uma lista de tarefas usando `ArrayList`.

### Módulo 3: Tratamento de Exceções
- **Try-catch**, `throws`, exceções personalizadas.
- **Exemplo**:

```java
public class Excecao {
    public static void main(String[] args) {
        try {
            int[] array = {1, 2, 3};
            System.out.println(array[5]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Erro: índice fora do limite!");
        }
    }
}
```

- **Exercício 3**: Crie um programa que divida dois números e trate a divisão por zero.

## Nível 3: Avançado

### Módulo 1: Programação Funcional
- **Lambdas e Streams**:
  - Processamento de coleções de forma funcional.
  - Exemplo:

```java
import java.util.Arrays;
import java.util.List;

public class StreamExemplo {
    public static void main(String[] args) {
        List<Integer> numeros = Arrays.asList(1, 2, 3, 4, 5);
        numeros.stream()
               .filter(n -> n % 2 == 0)
               .forEach(n -> System.out.println(n));
    }
}
```

- **Exercício 1**: Use Streams para filtrar números primos de uma lista.

### Módulo 2: Multithreading
- **Threads** e concorrência.
- **Exemplo**:

```java
public class ThreadExemplo extends Thread {
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println("Thread: " + i);
            try {
                Thread.sleep(1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }

    public static void main(String[] args) {
        ThreadExemplo t1 = new ThreadExemplo();
        t1.start();
    }
}
```

- **Exercício 2**: Crie duas threads que imprimam números pares e ímpares alternadamente.

### Módulo 3: Acesso a Banco de Dados (JDBC)
- **Conexão com banco de dados** (ex.: MySQL).
- **Exemplo**:

```java
import java.sql.*;

public class ConexaoBD {
    public static void main(String[] args) {
        String url = "jdbc:mysql://localhost:3306/teste";
        try (Connection conn = DriverManager.getConnection(url, "root", "senha")) {
            Statement stmt = conn.createStatement();
            ResultSet rs = stmt.executeQuery("SELECT * FROM usuarios");
            while (rs.next()) {
                System.out.println("Nome: " + rs.getString("nome"));
            }
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}
```

- **Exercício 3**: Crie um programa que insira e consulte dados em uma tabela de produtos.

### Módulo 4: Projeto Final
- **Sistema de gerenciamento de biblioteca**:
  - Crie um sistema com classes para `Livro`, `Usuario`, `Emprestimo`.
  - Use POO, coleções, tratamento de exceções e JDBC.
  - Funcionalidades: cadastrar livros, gerenciar empréstimos, consultar disponibilidade.
  - Exemplo de esboço:

```java
import java.util.ArrayList;

public class Livro {
    private String titulo;
    private boolean disponivel;

    public Livro(String titulo) {
        this.titulo = titulo;
        this.disponivel = true;
    }

    public String getTitulo() {
        return titulo;
    }

    public boolean isDisponivel() {
        return disponivel;
    }

    public void setDisponivel(boolean disponivel) {
        this.disponivel = disponivel;
    }
}

public class Biblioteca {
    private ArrayList<Livro> livros = new ArrayList<>();

    public void adicionarLivro(String titulo) {
        livros.add(new Livro(titulo));
    }

    public void exibirLivrosDisponiveis() {
        for (Livro livro : livros) {
            if (livro.isDisponivel()) {
                System.out.println(livro.getTitulo());
            }
        }
    }

    public static void main(String[] args) {
        Biblioteca bib = new Biblioteca();
        bib.adicionarLivro("Java para Iniciantes");
        bib.exibirLivrosDisponiveis();
    }
}
```
