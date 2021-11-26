Tarea 2 Actividad Grupal
================
Benjy Velasquez Fernandez & Diego Morante Suarez
24/11/2021

# Tarea N°2

### 1. ¿Qué cantidad de dinero sobra al repartir 10000$ entre 3 personas?

``` r
10000%%3
```

    ## [1] 1

### 2. ¿Es el número 4560 divisible por 3?

``` r
0 == (4560%%3)
```

    ## [1] TRUE

### 3. Construya un vector con los números enteros del 2 al 87. ¿Cuáles de esos números son divisibles por 7?

``` r
numeros_enteros <- c(2:87)
divisibles_7 <- (0 == numeros_enteros%%7)
which(divisibles_7 == TRUE)
```

    ##  [1]  6 13 20 27 34 41 48 55 62 69 76 83

``` r
numeros_enteros[c(6,13,20,27,34,41,48,55,62,69,76,83)]
```

    ##  [1]  7 14 21 28 35 42 49 56 63 70 77 84

### 4. Construya dos vectores, el primero con los números enteros desde 7 hasta 3, el segundo vector con los primeros cinco números positivos divisibles por 5.

``` r
prm_vctr <- c(seq(7,3,-1))
sgnd_vctr <- c(head(seq(0,100,5),5))
```

-   Sea A la condición de ser par en el primer vector.

``` r
A <- (0 == prm_vctr%%2)
which(A == TRUE)
```

    ## [1] 2 4

``` r
prm_vctr [c(2,4)]
```

    ## [1] 6 4

-   Sea B la condición de ser mayor que 10 en el segundo vector.

``` r
B <- which(sgnd_vctr >10)
sgnd_vctr [c(4,5)]
```

    ## [1] 15 20

-   ¿En cuál de las 5 posiciones se cumple A y B simultáneamente?

``` r
for (i in 1:5) {
  for (j in 1:5){
    if(i==j)
    {if(prm_vctr[i]==sgnd_vctr[j]){
      print(i)
    }
      
    }
  }
}
print("no hay datos")
```

    ## [1] "no hay datos"

### 5.Consulte este link (<https://github.com/fhernanb/Manual-de-R/blob/master/images/anecdota_gauss.PNG>) en el cual hay una anécdota de Gauss ni ̃no. Use R para obtener el resultado de la suma solicitada por el profesor del ni ̃no Gauss.

``` r
Gauss <- function(a) {
  r1 <- (a*(a+1))/2
  return(r1)
} 
Gauss(a = 1:100)
```

    ##   [1]    1    3    6   10   15   21   28   36   45   55   66   78   91  105  120
    ##  [16]  136  153  171  190  210  231  253  276  300  325  351  378  406  435  465
    ##  [31]  496  528  561  595  630  666  703  741  780  820  861  903  946  990 1035
    ##  [46] 1081 1128 1176 1225 1275 1326 1378 1431 1485 1540 1596 1653 1711 1770 1830
    ##  [61] 1891 1953 2016 2080 2145 2211 2278 2346 2415 2485 2556 2628 2701 2775 2850
    ##  [76] 2926 3003 3081 3160 3240 3321 3403 3486 3570 3655 3741 3828 3916 4005 4095
    ##  [91] 4186 4278 4371 4465 4560 4656 4753 4851 4950 5050

O tambien:

``` r
Gauss <- function(a) {
  (a*(a+1))/2
} 
Gauss(100)
```

    ## [1] 5050

### 6. Construya un vector con los siguientes elementos: 1, -4, 5, 9, -4. Escriba un procedimiento para extraer las posiciones donde está el valor mínimo en el vector.

``` r
vector_6 <- c(1, -4, 5, 9, -4)
min(vector_6)
```

    ## [1] -4

``` r
which(vector_6 == -4)
```

    ## [1] 2 5

### 7. Calcular 8!

``` r
factorial(8)
```

    ## [1] 40320

### 8. Evaluar la siguiente sumatoria 
$$\\sum\_{i=3}^{i=7} {e^i}$$

``` r
sumatoria1 <- function(i){
  exp(i)
}
sumatoria1(3:7)
```

    ## [1]   20.08554   54.59815  148.41316  403.42879 1096.63316

``` r
sum(sumatoria1(3:7))
```

    ## [1] 1723.159

### 9. Evaluar la siguiente productoria 
$$\\prod\_{i=1}^{i=10} \\log{\\sqrt{i}}$$

``` r
mifuncion <- function(i){
  log10(sqrt(i))
}
a <- mifuncion(1:10)
prod(a)
```

    ## [1] 0

### 10. Realizar una función que permita calcular el área de una corona circular.

``` r
Areacorona <- function(x,y){
  ((x)^2)/2*(y-sin(y))
}
Areacorona(4,pi/4)
```

    ## [1] 0.6263311

### 11. Construya un vector cualquiera e invierte, es decir, que el primer elemento quede de último, el segundo de penúltimo y así sucesivamente. Compare su resultado con el de la función **rev**

``` r
sort(c(1:10), decreasing = T)
```

    ##  [1] 10  9  8  7  6  5  4  3  2  1

``` r
vector_11 <- c(1:10)
sort(vector_11,decreasing = T)
```

    ##  [1] 10  9  8  7  6  5  4  3  2  1

``` r
rev(vector_11)
```

    ##  [1] 10  9  8  7  6  5  4  3  2  1

### 12. Calcular lo siguiente 
$$\\sum\_{i=10}^{100} {(i^3+4i^2)}$$

``` r
g <- 10:100
h <- g^3
i <- g^2
sum(h) + sum(4*i)
```

    ## [1] 26852735

### 13. Calcular lo siguiente 
$$\\sum\_{i=1}^{25} (\\frac{2^i}{i}+\\frac{3^i}{i^2})$$

``` r
a <- 1:25
b <- (2^a)/a
c <- (3^a)/a^2
sum(b) + sum(c)
```

    ## [1] 2129170437

### 14. Lea el siguiente archivo

14.1. Calcular el numero de variables del dataset

``` r
dataset <- read.delim("https://raw.githubusercontent.com/fhernanb/datos/master/Paises.txt")
length(dataset)
```

    ## [1] 5

14.2. ¿Cuantos paises hay en el dataset?

``` r
length(dataset$Pais)
```

    ## [1] 107

14.3. ¿Cual es el pais con mayor poblacion?

``` r
dataset$Pais [which.max(dataset$poblacion)]
```

    ## [1] "China_"

14.4. ¿Cual es el pais con alfabetizacion mas baja?

``` r
dataset$Pais [which.min(dataset$alfabetizacion)]
```

    ## [1] "Burkina_Faso"

### 15. En R hay unas bases de datos incluídas, una de ellas es la base de datos llamada mtcars. Para conocer las variables que están en mtcars usted puede escribir en la consola ?mtcars o también help(mtcars). De la base mtcars obtenga bases de datos que cumplan las siguientes condiciones.

###help(“mtcars”)

``` r
mtcars
```

    ##                      mpg cyl  disp  hp drat    wt  qsec vs am gear carb
    ## Mazda RX4           21.0   6 160.0 110 3.90 2.620 16.46  0  1    4    4
    ## Mazda RX4 Wag       21.0   6 160.0 110 3.90 2.875 17.02  0  1    4    4
    ## Datsun 710          22.8   4 108.0  93 3.85 2.320 18.61  1  1    4    1
    ## Hornet 4 Drive      21.4   6 258.0 110 3.08 3.215 19.44  1  0    3    1
    ## Hornet Sportabout   18.7   8 360.0 175 3.15 3.440 17.02  0  0    3    2
    ## Valiant             18.1   6 225.0 105 2.76 3.460 20.22  1  0    3    1
    ## Duster 360          14.3   8 360.0 245 3.21 3.570 15.84  0  0    3    4
    ## Merc 240D           24.4   4 146.7  62 3.69 3.190 20.00  1  0    4    2
    ## Merc 230            22.8   4 140.8  95 3.92 3.150 22.90  1  0    4    2
    ## Merc 280            19.2   6 167.6 123 3.92 3.440 18.30  1  0    4    4
    ## Merc 280C           17.8   6 167.6 123 3.92 3.440 18.90  1  0    4    4
    ## Merc 450SE          16.4   8 275.8 180 3.07 4.070 17.40  0  0    3    3
    ## Merc 450SL          17.3   8 275.8 180 3.07 3.730 17.60  0  0    3    3
    ## Merc 450SLC         15.2   8 275.8 180 3.07 3.780 18.00  0  0    3    3
    ## Cadillac Fleetwood  10.4   8 472.0 205 2.93 5.250 17.98  0  0    3    4
    ## Lincoln Continental 10.4   8 460.0 215 3.00 5.424 17.82  0  0    3    4
    ## Chrysler Imperial   14.7   8 440.0 230 3.23 5.345 17.42  0  0    3    4
    ## Fiat 128            32.4   4  78.7  66 4.08 2.200 19.47  1  1    4    1
    ## Honda Civic         30.4   4  75.7  52 4.93 1.615 18.52  1  1    4    2
    ## Toyota Corolla      33.9   4  71.1  65 4.22 1.835 19.90  1  1    4    1
    ## Toyota Corona       21.5   4 120.1  97 3.70 2.465 20.01  1  0    3    1
    ## Dodge Challenger    15.5   8 318.0 150 2.76 3.520 16.87  0  0    3    2
    ## AMC Javelin         15.2   8 304.0 150 3.15 3.435 17.30  0  0    3    2
    ## Camaro Z28          13.3   8 350.0 245 3.73 3.840 15.41  0  0    3    4
    ## Pontiac Firebird    19.2   8 400.0 175 3.08 3.845 17.05  0  0    3    2
    ## Fiat X1-9           27.3   4  79.0  66 4.08 1.935 18.90  1  1    4    1
    ## Porsche 914-2       26.0   4 120.3  91 4.43 2.140 16.70  0  1    5    2
    ## Lotus Europa        30.4   4  95.1 113 3.77 1.513 16.90  1  1    5    2
    ## Ford Pantera L      15.8   8 351.0 264 4.22 3.170 14.50  0  1    5    4
    ## Ferrari Dino        19.7   6 145.0 175 3.62 2.770 15.50  0  1    5    6
    ## Maserati Bora       15.0   8 301.0 335 3.54 3.570 14.60  0  1    5    8
    ## Volvo 142E          21.4   4 121.0 109 4.11 2.780 18.60  1  1    4    2

15.1. Autos que tengan un rendimiento menor a 18 millas por galón de
combustible.

``` r
row.names(mtcars)[which(mtcars$mpg <18)]
```

    ##  [1] "Duster 360"          "Merc 280C"           "Merc 450SE"         
    ##  [4] "Merc 450SL"          "Merc 450SLC"         "Cadillac Fleetwood" 
    ##  [7] "Lincoln Continental" "Chrysler Imperial"   "Dodge Challenger"   
    ## [10] "AMC Javelin"         "Camaro Z28"          "Ford Pantera L"     
    ## [13] "Maserati Bora"

15.2. Autos que tengan 4 cilindros.

``` r
row.names(mtcars)[which(mtcars$cyl == 4)]
```

    ##  [1] "Datsun 710"     "Merc 240D"      "Merc 230"       "Fiat 128"      
    ##  [5] "Honda Civic"    "Toyota Corolla" "Toyota Corona"  "Fiat X1-9"     
    ##  [9] "Porsche 914-2"  "Lotus Europa"   "Volvo 142E"

15.3. Autos que pesen más de 2500 libras y tengan transmisión manual.

``` r
row.names(mtcars)[which(mtcars$wt >2,5 & mtcars$am =="1")]
```

    ##  [1] "Mazda RX4"           "Mazda RX4 Wag"       "Datsun 710"         
    ##  [4] "Hornet 4 Drive"      "Hornet Sportabout"   "Valiant"            
    ##  [7] "Duster 360"          "Merc 240D"           "Merc 230"           
    ## [10] "Merc 280"            "Merc 280C"           "Merc 450SE"         
    ## [13] "Merc 450SL"          "Merc 450SLC"         "Cadillac Fleetwood" 
    ## [16] "Lincoln Continental" "Chrysler Imperial"   "Fiat 128"           
    ## [19] "Toyota Corona"       "Dodge Challenger"    "AMC Javelin"        
    ## [22] "Camaro Z28"          "Pontiac Firebird"    "Porsche 914-2"      
    ## [25] "Ford Pantera L"      "Ferrari Dino"        "Maserati Bora"      
    ## [28] "Volvo 142E"

###16. La ecuación de tiempo es la diferencia entre el tiempo solar
medio y el tiempo solar aparente (Referencia).
“<http://pbarbier.com/eqtime/eqtime.html>” Si bien esta varía, la forma
analítica de esta ecuación se muestra a continuación (Usar x como un
rango de 0 a 365). Replicar el gráfico:
*y* = 2(*x*−81)/365
*f*(*y*) = 9, 87*s**e**n*(2*y*) − 7, 53*c**o**s*(*y*) − 1, 5*s**e**n*(*y*)

``` r
x <- 0:365
y <- 2*pi*(x-81)/365

Funcion01 <- function(y) {
  x <- (9.87*2*sin(y)*cos(y))-(7.53*cos(y))-(1.5*sin(y))
  return(x)
}

x <-seq(as.Date("2021-01-01"), as.Date("2022-01-01"), "day")

plot(x, Funcion01(y), ylab = "Minutos", xlab = "Meses", col ="red", type = "l", lwd = 3, lty = 2)

mtext("Mathematical Astronomy Morsels, Jean Meeus. 1997", side = 3, adj = 0)

title("Ecuación del tiempo", adj = 0.000001, line = 1.5)
```

![](Tarea02_programacion_files/figure-gfm/unnamed-chunk-27-1.png)<!-- -->
