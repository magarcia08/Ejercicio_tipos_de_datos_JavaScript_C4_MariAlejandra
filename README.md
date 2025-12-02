## Actividad de números randoms


# En este espacio explicaremos la utilidad del codigo realizado en nuestro proyecto

## Primer paso:

- Creación de html en donde abarcaremos la actividad en la parte de script

## Segundo paso explicacion del script:

    document.getElementById("simularBtn").addEventListener("click", () => {

Lo usamos para la creacion del boton y que este envie el evento al darle click

    const tiradas = 10_000_000;

Declaramos la variable de las n veces que vamos a realizar la simulacion

        const contador = {
                2: 0, 3: 0, 4: 0, 5: 0, 6: 0,
                7: 0, 8: 0, 9: 0, 10: 0, 11: 0, 12: 0
            };

Este contador es una forma de evaluar cuantas veces cae el numero y asi evaluar cual es el numero que mas veces cae

            for (let i = 0; i < tiradas; i++) {
                const dado1 = Math.floor(Math.random() * 6) + 1;
                const dado2 = Math.floor(Math.random() * 6) + 1;
                const suma = dado1 + dado2;

                contador[suma]++;
            }

Hacemos el for para hacer el ciclo, inicia de 0 y aumenta de acuerdo a las tiradas que son (10_000_000)

        let maxNumero = null;
            let maxVeces = -1;

            for (const numero in contador) {
                if (contador[numero] > maxVeces) {
                    maxVeces = contador[numero];
                    maxNumero = numero;
                }
            }

Luego hacemos otro ciclo para calcular las veces y cada numero que tendra sus numero aleatorios

const texto =
                "Conteo:\n" +
                JSON.stringify(contador, null, 2) +
                `\n \n  El número que mas veces cayó fue: ${maxNumero} con ${maxVeces} veces.`;

            document.getElementById("resultados").textContent = texto;
        });

acá hacemos un pequeño codigo que muestra cual fue el resultado del ciclo for dado anteriormente