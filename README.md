# codecrafteam
## NAND2TETRIS

En la ejecución de la primera práctica, se optó por la herramienta nand2tetris. En un principio, se llevó a cabo una exploración minuciosa de su sitio web y de los recursos disponibles. Se dedicó tiempo a reflexionar acerca de la valiosa utilidad y el material educativo que esta plataforma ofrecía. Esto permitió comprender cómo nand2tetris se convierte en un recurso enriquecedor para adquirir conocimientos adicionales en el ámbito de la arquitectura de computadoras.

## Compuerta Not 


La compuerta NOT se crea a partir de una Compuerta NAND con una única entrada, pero debido a la solicitud del programa de dos entradas, se suministra la misma entrada dos veces, generando así la tabla de verdad que es equivalente a la de la compuerta NOT.

![Image text](https://github.com/Arquitectura-Grupo-6/codecrafteam/blob/main/lab1/images/not.png)

<pre>
    CHIP Not {
    IN in;
    OUT out;

    PARTS:
    Nand(a=in, b=in, out=out);
    }
</pre>


## Compuerta AND 

La compuerta AND se construye mediante el uso de dos compuertas NAND. La primera genera la función AND inversa, mientras que la segunda funciona como un inversor para obtener la salida de AND en su forma normal. La segunda compuerta NAND puede ser reemplazada por una compuerta NOT sin que la tabla de verdad resultante experimente cambios.

![Image text](https://github.com/Arquitectura-Grupo-6/codecrafteam/blob/main/lab1/images/and.png)

<pre>
CHIP And {
    IN a, b;
    OUT out;

    PARTS:
    Nand(a=a, b=b, out=nad1);
    Nand(a=nad1, b=nad1, out=out);
}
</pre>


## Compuerta OR

La compuerta OR se obtiene mediante una compuerta NAND que toma como entradas las salidas de un inversor o de una compuerta NAND individual que posee entradas individuales.

![Image text](https://github.com/Arquitectura-Grupo-6/codecrafteam/blob/main/lab1/images/or.png)

<pre>
CHIP Or {
    IN a, b;
    OUT out;

    PARTS:
    Nand(a=a, b=a, out=nad1);
    Nand(a=b, b=b, out=nad2);
    Nand(a=nad1, b=nad2, out=out);
}
</pre>

## Compuerta XOR


La compuerta XOR, también conocida como “OR exclusiva”, se le denomina la compuerta de “algunos pero no todos”, su expresión Booleana es una suma binaria de un dígito cada uno y el resultado obtenido será la salida. La salida tiene un estado activo “1” al tener las entradas en estados diferentes

![Image text](https://github.com/Arquitectura-Grupo-6/codecrafteam/blob/main/lab1/images/xor1.png)

<pre>
CHIP Xor {
    IN a, b;
    OUT out;

    PARTS:
    	Nand(a=a,b=b,out=nad1);
    	Nand(a=a,b=nad1,out=nad2);
   	Nand(a=nad1,b=b,out=nad3);
	Nand(a=nad2,b=nad3,out=out);
}
</pre>

