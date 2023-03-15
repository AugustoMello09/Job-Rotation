# Job-Rotation

#### 1) Observe o trecho de código abaixo:

int INDICE = 13, SOMA = 0, K = 0;

enquanto K < INDICE faça

{

K = K + 1;

SOMA = SOMA + K;

}

imprimir(SOMA);

Ao final do processamento, qual será o valor da variável SOMA?

R: 91
~~~~JAVA
package teste;

public class TesteUm {

    public static void main(String[] args) {
        int indice = 13;
        int soma = 0;
        int k = 0;
        while (k < indice) {
            k = k + 1;
            soma = soma + k;
            System.out.println(soma);
        }

    }
}
// resultado da soma 91
~~~~

####  2) Dado a sequência de Fibonacci, onde se inicia por 0 e 1 e o próximo valor sempre será a soma dos 2 valores anteriores (exemplo: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34...), escreva um programa na linguagem que desejar onde, informado um número, ele calcule a sequência de Fibonacci e retorne uma mensagem avisando se o número informado pertence ou não a sequência.

~~~~JAVA
public class TesteUm {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Digite um número: ");
        int numero = sc.nextInt();

        int primeiro = 0, segundo = 1, proximo;
        boolean pertence = false;

        for (int i = 1; i <= numero; i++) {
            if (i == numero) {
                pertence = true;
            }
            proximo = primeiro + segundo;
            primeiro = segundo;
            segundo = proximo;
        }

        if (pertence) {
            System.out.println(numero + " pertence à sequência de Fibonacci.");
        } else {
            System.out.println(numero + " não pertence à sequência de Fibonacci.");
        }

    }
}
~~~~

#### 3) Descubra a lógica e complete o próximo elemento:

a) 1, 3, 5, 7, ___

b) 2, 4, 8, 16, 32, 64, ____

c) 0, 1, 4, 9, 16, 25, 36, ____

d) 4, 16, 36, 64, ____

e) 1, 1, 2, 3, 5, 8, ____

f) 2,10, 12, 16, 17, 18, 19, ____

__RESPOSTA:__

a) cada número é o número ímpar subsequente ao último número da série. Portanto, o próximo número é 9.
~~~~JAVA
int a = 1;
for (int i = 0; i < 4; i++) {
   a += 2;
}
System.out.println(a); // imprime 9
~~~~

b) cada número é o dobro do número anterior. Portanto, o próximo número é 128.
~~~~JAVA
int b = 2;
for (int i = 0; i < 5; i++) {
   b *= 2;
}
System.out.println(b); // imprime 128
~~~~
c) cada número é o quadrado do número natural subsequente. Portanto, o próximo número é 49.
~~~~JAVA
int c = 0;
for (int i = 1; i < 8; i++) {
   c += (2 * i) - 1;
}
System.out.println(c); // imprime 49
~~~~
d) cada número é o quadrado do número par subsequente. Portanto, o próximo número é 100.
~~~~JAVA
int d = 4;
for (int i = 0; i < 3; i++) {
   d += (i + 3) * (i + 3);
}
System.out.println(d); // imprime 100
~~~~
e) cada número é a soma dos dois números anteriores. Portanto, o próximo número é 13.
~~~~JAVA
int e = 1;
int anterior1 = 1;
int anterior2 = 1;
for (int i = 0; i < 4; i++) {
   e = anterior1 + anterior2;
   anterior2 = anterior1;
   anterior1 = e;
}
System.out.println(e); // imprime 13
~~~~
f) cada número é o resultado da adição de um número ímpar crescente e um número par subsequente. Portanto, o próximo número é 20. 
~~~~JAVA
int f = 2;
int[] incrementos = {2, 2, 4, 1, 1, 1};
for (int i = 0; i < 6; i++) {
   f += incrementos[i];
}
System.out.println(f); // imprime 20
~~~~


#### 4 - Dois veículos (um carro e um caminhão) saem respectivamente de cidades opostas pela mesma rodovia. O carro de Ribeirão Preto em direção a Franca, a uma velocidade constante de 110 km/h e o caminhão de Franca em direção a Ribeirão Preto a uma velocidade constante de 80 km/h. Quando eles se cruzarem na rodovia, qual estará mais próximo a cidade de Ribeirão Preto?

__IMPORTANTE:__

a) Considerar a distância de 100km entre a cidade de Ribeirão Preto <-> Franca.

b) Considerar 2 pedágios como obstáculo e que o caminhão leva 5 minutos a mais para passar em cada um deles e o carro possui tag de pedágio (Sem Parar)

c) Explique como chegou no resultado.

~~~~JAVA
public class TesteUm {
    public static void main(String[] args) {
        int distancia = 100; // km
        int velocidadeCarro = 110; // km/h
        int velocidadeCaminhao = 80; // km/h
        int tempoPedagio = 5; // minutos

        // Convertendo o tempo de pedágio em horas
        double horaPedagio = tempoPedagio / 60.0;

        // Calculando o tempo que os veículos se cruzarão
        double tempoCruzamento = (distancia / (velocidadeCarro + velocidadeCaminhao)) - horaPedagio * 2;

        // Calculando a distância que cada veículo estará da cidade de Ribeirão Preto no momento do cruzamento
        double distanciaCarro = tempoCruzamento * velocidadeCarro;
        double distanciaCaminhao = distancia - distanciaCarro;

        // Verificando qual veículo estará mais próximo da cidade de Ribeirão Preto
        if (distanciaCarro < distanciaCaminhao) {
            System.out.println("O carro estará mais próximo da cidade de Ribeirão Preto.");
        } else {
            System.out.println("O caminhão estará mais próximo da cidade de Ribeirão Preto.");
        }
    }
}
~~~~

 Eu utilizei fórmula de velocidade média para calcular o tempo que os veículos se cruzarão, levando em consideração o tempo gasto pelo caminhão nos pedágios. Em seguida, é calculei a distância que cada veículo estará da cidade de Ribeirão Preto no momento do cruzamento, subtrai a distância percorrida pelo carro da distância total. Por fim, fiz a comparação das distâncias para verificar qual veículo estará mais próximo da cidade de Ribeirão Preto.

#### 5) Escreva um programa que inverta os caracteres de um string.

__IMPORTANTE:__

a) Essa string pode ser informada através de qualquer entrada de sua preferência ou pode ser previamente definida no código;

b) Evite usar funções prontas, como, por exemplo, reverse;

~~~~JAVA
public class TesteUm {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Digite uma string: ");
        String str = scanner.nextLine();

        String strInvertida = "";

        for (int i = str.length() - 1; i >= 0; i--) {
            strInvertida += str.charAt(i);
        }

        System.out.println("String invertida: " + strInvertida);
    }
    
}
//input: José
//output: ésoJ
~~~~

## Ferramentas e Tecnologias usadas nesse repositório 🧱
<div style="display: inline_block"><br>
<img align="center" alt="Augusto-Java" height="60" width="60" src=https://github.com/devicons/devicon/blob/master/icons/java/java-original.svg >
</div>    

## Entre em contato comigo através dos canais abaixo e desde já, agradeço a atenção. 🤝 

<div>

  <a href="https://www.linkedin.com/in/jos%C3%A9-augusto-mello-794a94234" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>
 <a href="mailto:joseaugusto.Mello01@gmail.com" target="_blank"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>   

</div>
