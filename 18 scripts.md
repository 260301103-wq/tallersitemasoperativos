1. Hola mundo

bash
#!/bin/bash
echo "Hola mundo"
---
2. Hola mundo con variable
bash
#!/bin/bash
SALUDO="Hola mundo"
echo -n "Este script te dice: "
echo ${SALUDO}
---
3. Uso de variables
bash
#!/bin/bash
una_variable=666
MI_NOMBRE="Richard"
NOMBRES="Iñigo Asier Sten Roberto Pello"
BOOLEANO=true

echo "Echemos un ojo a las variables "
echo "Un número: ${una_variable}"
echo "Un nombre ${MI_NOMBRE}"
echo "Un grupo de nombres: ${NOMBRES}"

echo "Has invocado el script pasándome ${0} eta ${1} "
echo "Me has pasado $# argumentos"
echo "Los argumentos son: $@"
echo "Mi directorio actual: ${PWD} y mi usuario ${UID}"
-------------------------------------------------------------
### 4. Uso de Arrays
bash
#!/bin/bash
asociaciones[0]="Gruslin"
asociaciones[1]="Hackresi"
asociaciones[2]="NavarradotNET"
asociaciones[3]="Riberlug"

partidos=("UPN" "PSN" "CDN" "IUN" "Nafarroa BAI" "RCN" )
numeros=(15 23 45 42 23 1337 23 666 69)

echo "${asociaciones[0]} es una asociación, ${partidos[1]} un partido"
echo "Tamaño de asociaciones: ${#asociaciones[@]}"
echo "Tamaño de partidos: ${#partidos[@]}"
-------------------------------------------------------------
### 5. Substrings y valores por defecto
bash
#!/bin/bash
NOMBRE="Navarrux Live edition"
echo "${NOMBRE} una parte ${NOMBRE:8} y otra ${NOMBRE:8:4}"

SINVALOR=
echo "Variable SINVALOR: ${SINVALOR:-31337} eta ${VACIO:-'Miguel Indurain'}"
echo "La variable SINVALOR no tiene valor alguno: ${SINVALOR} "

echo "Variable SINVALOR: ${SINVALOR:=31337} eta ${VACIO:='Miguel Indurain'}"
echo "La variable SINVALOR ahora tiene: ${SINVALOR} "

PROGRAMA='snifit'
echo "valor de PROGRAMA: ${PROGRAMA:+'tcpdump'} y ahora ${PROGRAMA}"

echo "Valor de: ${EJEMPLO:?'Roberto'} y luego ${EJEMPLO}"

echo "Variables que empiezan con P:"
for i in ${!P*}; do echo $i ; done
-------------------------------------------------------------
### 6. Operaciones Aritméticas
bash
#!/bin/bash
VALOR1=23
VALOR2=45

RESULTADO=$(expr ${VALOR1} + ${VALOR2})
echo "Resultado: ${RESULTADO}"

RESULTADO=$(expr ${VALOR1} + ${VALOR2} + 3)
echo "Resultado: ${RESULTADO}"

VALOR1=5
VALOR2=4
echo "${VALOR1} y ${VALOR2}"

RESULTADO=$[${VALOR1} + ${VALOR2} + 2]
echo "Ahora: ${VALOR1} + ${VALOR2} + 2 = ${RESULTADO}"

RESULTADO=$[${VALOR1} + ${VALOR2} * 3]
echo "Ahora: ${VALOR1} + ${VALOR2} * 3 = ${RESULTADO}"
-------------------------------------------------------------
### 7. Operaciones Lógicas
bash
#!/bin/bash
boolean=true

$boolean && echo "OK" || echo "no es true"

otrobool=!${boolean}
test $otrobool || echo "Ahora es falso"

valor=6
test $valor -le 6 && echo "Se cumple"

nuevo=$valor
test $nuevo -eq $valor && echo "Son los mismos"
echo "Ahora $nuevo es lo mismo que $valor"
### 8. Condicionales (if y test)
bash
#!/bin/bash
VARIABLE=45

if [ ${VARIABLE} -gt 0 ]; then
    echo "${VARIABLE} es mayor que 0"
fi

if [ -e /etc/shadow ]
then
    echo "OK, parece que tienes un sistema con shadow pass"
fi
-------------------------------------------------------------
### 9. Estructura if-else
bash
#!/bin/bash
OTRA=-23

if [ ${OTRA} -lt 0 ]
then
    echo "${OTRA} es menor que 0"
else
    echo "${OTRA} es mayor que 0"
fi
-------------------------------------------------------------
### 10. Estructura if-elseif
bash
#!/bin/bash
echo -n "Mete un valor: "
read VALOR1
echo -n "Mete otro valor: "
read VALOR2

echo "Has introducido los valores ${VALOR1} y ${VALOR2} "

if [ ${VALOR1} -gt ${VALOR2} ]
then
    echo "${VALOR1} es mayor que ${VALOR2}"
elif [ ${VALOR1} -lt ${VALOR2} ]
then
    echo "${VALOR1} es menor que ${VALOR2}"
else
    echo "${VALOR1} y ${VALOR2} son iguales"
fi
-------------------------------------------------------------
### 11. Estructura Case
bash
#!/bin/bash
NOMBRE=""
echo -n "Dame un nombre: "
read NOMBRE

case ${NOMBRE} in
    iñigo)
        echo "${NOMBRE} dice: me dedico a Navarrux"
        ;;
    sten)
        echo "${NOMBRE} dice: tengo un blog friki"
        ;;
    asier)
        echo "${NOMBRE} dice: .NET me gusta"
        ;;
    pello)
        echo "${NOMBRE} dice: el shell mola"
        ;;
    *)
        echo "A ${NOMBRE} no lo conozco"
        ;;
esac
-------------------------------------------------------------
###  12. Iteración For
bash
#!/bin/bash
echo "FOR simple: "
for i in a b c d e f g h i
do
    echo "letra: $i"
done

NOMBRES="Iñigo Sten Asier Pello Roberto"
echo "FOR simple para recorrer un array: "
echo "Participantes en la 4party: "
for i in ${NOMBRES}
do
    echo ${i}
done

echo "FOR con el resultado de un comando"
for i in $(cat direcciones.txt 2>/dev/null)
do
    echo ${i}
done

echo "FOR con ficheros"
for i in *.sh
do
    ls -lh ${i}
done

echo "FOR clásico "
for (( cont=0 ; ${cont} < 10 ; cont=$(expr $cont + 1) ))
do
    echo "Ahora valgo> ${cont}"
done
-------------------------------------------------------------
### 13. Iteración While
bash
#!/bin/bash
echo "WHILE en marcha"
cont=0

while (test ${cont} -lt 100)
do
    cont=$(expr $cont + 10)
    echo "Valor del contador: ${cont}"
done

echo "Valor final del contador: ${cont}"
-------------------------------------------------------------
### 14. Iteración Until
bash
#!/bin/bash
echo "Estructura until"
cont=15

until (test ${cont} -lt 0)
do
    cont=$(expr $cont - 1)
    echo "Valor del contador: ${cont}"
done

echo "Valor final del contador: ${cont}"
-------------------------------------------------------------
### 15. Iteración Select (Menú)
bash
#!/bin/bash
echo "Select de distros"
DISTROS="Debian Ubuntu Navarrux Gentoo Mandriva"
echo "Selecciona la mejor opción por favor: "

select resultado in ${DISTROS}
do
    (test ${#resultado} -ne 0 ) && break
    echo "Selecciona la mejor opción por favor: ${resultado}"
done

echo "Sistema seleccionado: [${resultado}] longitud de cadena: ${#resultado}"
-------------------------------------------------------------
### 16. Funciones
bash
#!/bin/bash
RESULTADO=0

muestrapantalla () {
    echo "Valores: $0> $1 y $2 y $3"
}

sumame () {
    echo "Estamos en la función: ${FUNCNAME}"
    echo "Parametros: $1 y $2"
    RESULTADO=$(expr $1 + $2)
    return 0
}

boom () {
    echo "No ejecutes esto... "
    boom
}

muestrapantalla 3 4 "epa"

sumame 45 67 && echo "OK" || echo "Ocurrió un error"

echo "Resultado: ${RESULTADO} $!"
-------------------------------------------------------------
### 17. Librerías
libreria.sh:

bash
#!/bin/bash
RESULTADO=0
muestrapantalla () {
    echo "Valores: $0> $1 y $2 y $3"
}
sumame () {
    echo "Estamos en la función: ${FUNCNAME}"
    echo "Parametros: $1 y $2"
    RESULTADO=$(expr $1 + $2)
    return 0
}
Script principal:

bash
#!/bin/bash
source libreria.sh

muestrapantalla 69 123 "epa"
sumame 1337 3389 && echo "OK" || echo "Ocurrió un error"
echo "Resultado: ${RESULTADO} $!"
-------------------------------------------------------------
### 18. Señales y Colores ANSI
Señales:

bash
#!/bin/bash
funcion () {
    echo "Se ha recibido una señal: ${FUNCNAME} ${0}"
}

trap "funcion" INT QUIT TSTP

while true
do
    sleep 2
    echo "uff que sueno..."
done
