## Actividad de números randoms


# En este espacio explicaremos la utilidad del codigo realizado en nuestro proyecto

## Primer paso:

- Creación de html en donde abarcaremos la actividad en la parte de script

## Segundo paso explicacion del script:

    document.getElementById("simularBtn").addEventListener("click", () => {

Lo usamos para la creacion del boton y que este envie el evento al darle click

    const tiradas = 10_000_000;

Declaramos la variable de las n veces que vamos a realizar la simulacion

         const dado1 = {
            1: 0, 2: 0, 3: 0, 4: 0, 5: 0, 6: 0
        };
        
        const dado2 = {
            1: 0, 2: 0, 3: 0, 4: 0, 5: 0, 6: 0
        };

Este contador es una forma de evaluar cuantas veces cae el numero y asi evaluar cual es el numero que mas veces cae

           for (let i = 0; i < tiradas; i++) {
        
            const cara1 = Math.floor(Math.random() * 6) + 1;
            const cara2 = Math.floor(Math.random() * 6) + 1;
        
            dado1[cara1]++;
            dado2[cara2]++;
        }

Hacemos el for para hacer el ciclo, inicia de 0 y aumenta de acuerdo a las tiradas que son (10_000_000)

        function obtenerMax(dado) {
            let maxNumero = null;
            let maxVeces = -1;
        
            for (const cara in dado) {
                if (dado[cara] > maxVeces) {
                    maxVeces = dado[cara];
                    maxNumero = cara;
                }
            }
        
            return { maxNumero, maxVeces };
        }

Luego hacemos otro ciclo para calcular las veces y cada numero que tendra sus numero aleatorios
const resultadoDado1 = obtenerMax(dado1);
        const resultadoDado2 = obtenerMax(dado2);
        
        console.log("Resultados del Dado 1:");
        console.log(dado1);
        console.log(`La cara que más cayó en el Dado 1 fue: ${resultadoDado1.maxNumero} con ${resultadoDado1.maxVeces} veces. `);
        
        console.log("\nResultados del Dado 2:");
        console.log(dado2);
        console.log( `La cara que más cayó en el Dado 2 fue: ${resultadoDado2.maxNumero} con ${resultadoDado2.maxVeces} veces.`);
        

acá hacemos un pequeño codigo que muestra cual fue el resultado del ciclo for dado anteriormente