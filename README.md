<h1>No es tan aleatorio</h1>
<ol>
<li><h2>Enunciado:</h2></li>
	<p>Se tiene un número determinado de bolas blancas (w) y negras (b), con una cantidad de bolas suplementarias infinita.
	Se pide al público que retire un par de bolas. Si ambas bolas son del mismo color, se añade una bola blanca. En el caso contrario, una negra.
	Nuestra misión es adivinar el color de la última bola que queda.</p>
<li><h2>Solución:</h2></li>
	<p>Saber si saldrá blanca o negra depende únicamente del núnmero de bolas negras. Si es par saldrá blanca y si es impar saldrá negra.</p>
<li><h2>Demostración:</h2></li>
	<p>Hay varias formas de demostrarlo, he aquí un par:</p>
	<ol>
		<li><h3>Por árboles</h3></li>
		<p>Vamos a hacer a fuerza bruta varios escenarios a ver que sucede.</p>
		<p>2 Negras y 2 Blancas:</p>
		<img src="https://github.com/user-attachments/assets/9433d7f8-3b3d-4fac-8a95-5cad117321af">
		<p>3 Negras y 3 Blancas:</p>
		<p>Como notamos, si hay la misma cantidad y además, son pares, sale Blanca al final.</p>
		<li><h3>Por matematicas</h3></li>
		<p>Tomemos el primer caso (2 negras y 2 blancas), de la rama superior tomamos 2 bolas negras (b-=2) y añadimos una blanca (w++). Nos quedamos sin bolas negras entonces se vuelve un bucle donde retiramos 2 bolas blancas, añadimos una, dando un saldo neto de una bola blanca menos (w--). Dando como resultado una bola Blanca al final.</p>
		<p>La segunda rama y tercera varian en el proceso, pero convergen rapido. La segunda es una bola de cada color menos (w--;b--) y añadimos una negra (b++). Con un resultado neto de una bola Blanca menos (w--). Mientras tanto en la tercera retiramos dos bolas Blancas (w-=2) y ponemos una Blanca (w++). En neto, hemos retirado una bola Blanca (w--). Con esto se demuestra que es lo mismo sacar dos bolas Blancas que dos bolas de colores distintos.</p>
		<li><h3>Por deducción</h3></li>
		<p>La última bola depende del factor de la última pareja, si ambas son del mismo color (Blanca-Blanca o Negra-Negra), la última bola será Blanca, por lo contraria, será una Negra.</p>
	</ol>
<li><h2>Implementación:</h2></li>
	<p>En varios lenguages de programación como C++, JavaScript, PHP o el mismo Java, existe el operador condicional: <i>A?B:C</i></p>
	<p>Funciona de la siguiente manera: A es la condición, B es el valor que devuelve si A es verdadero, C es el que devuelve si A es falso.</p>
		
  	class Kata {
		public static String notSoRandom(int b, int w) {
    		return b%2==0?"White":"Black";
  		}
	}

 <p>Notemos entonces lo que se hace A es <i>b%2==0</i><br> La condición es que si el modulo de la division entre 2 fuera 0, devuelve B. En este caso, "White". Por lo contrario, devuelve C. En este caso, "Black".</p>
	<p>El operador condicional es útil en los casos donde lo que varia según la condición es un único valor. Por lo contrario, sería preferible un <i>if</i> o un <i>switch</i>, dependiendo del contexto en el que trabajamos.</p>
</ol>
