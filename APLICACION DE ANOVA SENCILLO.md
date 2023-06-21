#En este ejemplo cargaremos una base de datos en excel

#EJEMPLO: IMAGINEMOSNO QUE TENEMOS DOS PRODUCTOS A PRUEBA VEREMOS COMO INFLUEYEN SOBRE LA TEMPERATURA Y HUMEDAD 
-EN OTRO CASO PODRIAS APLICARLO SI FUESEN INSECTOS QUE ATACAN UN CULTIVO- TEMPERATURA Y HUMEDAD PODRIAS CAMBIARLO POR EL NOMBRE DEL INSECTO--- BUENO EL PRINCIPIO SERIA EL MISMO.

#PRODUCTO	TEMPERATURA	HUMEDAD
Con Producto	48	76.12
Con Producto	49	77.16
Sin Producto	46	78.2
Sin Producto	58	75.36 

#ESTA TABLA CONTIENE.... MAS DATOS

#EN ESTE CASO CARGUE EL EXCELL DESDE EXPORTAR, Y LUEGO LO TRANSFORME EN UN DATAFRAME
#LE LLAME "ANOVA"
df <-ANOVA

ESPERA CABALLERO--- ANTES DE SEGUIR RECUERDA DESCARGAR 
UFFFF
library(ggpubr)
library(mlbench)
library(gridExtra)
library(ggpubr)
library(ggplot2)
 
 AHORA SÌ!!


# Realiza el ANOVA
anova_result <- aov(TEMPERATURA ~ PRODUCTO, data = df)

# Realiza el ANOVA EN ESTE CASO PARA TEMPERATURA- REALIZALO PARA AMBAS VARIABLE- MI CASO HUMEDAD Y TEMPERATURA.
anova_result <- aov(TEMPERATURA ~ PRODUCTO, data = df)

# Imprime los resultados del ANOVA
summary(anova_result)


# Realiza las pruebas post hoc de Tukey
posthoc_result <- TukeyHSD(anova_result)

# Imprime los resultados de las pruebas post hoc
print(posthoc_result)


 library(ggpubr)

# Gráfico de caja y bigote con puntos de dispersión por temperatura
p <- ggboxplot(df, x = "PRODUCTO", y = "TEMPERATURA",
               color = "PRODUCTO", palette = "jco",
               add = "jitter")

# Añadir valor p de la prueba de comparación de medias
p + stat_compare_means()

# Cambiar el método de prueba
p + stat_compare_means(method = "t.test")

 
 
 RECUERDE HACER EL GRAFICO PARA AMBAS HUMEDAD Y TEMPERATURA
 
RESULTADO:

![humedad](https://github.com/Megasoma2222/Biologia-ecologia-y-diversidad/assets/137216764/0211f591-8be8-40bb-918b-f073e93467c5)

![temperatura](https://github.com/Megasoma2222/Biologia-ecologia-y-diversidad/assets/137216764/1cb232cb-e107-4d08-99c0-0a04e0b5a493)


