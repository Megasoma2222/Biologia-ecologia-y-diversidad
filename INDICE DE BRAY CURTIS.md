# INDICES DE DIVERSIDAD BIOLOGIA - SENCILLO
INDICES PARA BIOLOGOS DE CAMPO

PRIMER IDICE ES EL DE BRAY CURTIS - LEE POR FAVOR COMO APLICARLO Y QUE SIGNIFICA ESTE ANALISIS.

# PASO1-PRIMERO REALIZAREMOS LA DATAFRAME, EN ESTE CASO SERAN DIFERENTES ESPECIES RECOLECTADAS EN DIFERENTES NIVELES ALTITUDINALES - UNA MONTAÑA- 

# Paso 2: Crear una matriz de datos con los valores proporcionados
datos <- matrix(c(
  12, 12, 23, 51, 31, 1, 23, 43,
  31, 31, 3, 1, 2, 2, 32, 21,
  1, 12, 14, 2, 2, 5, 3, 23,
  2, 34, 31, 31, 12, 24, 34, 34
), nrow = 4, byrow = TRUE)

# Paso 3: Calcular la matriz de distancia de Bray-Curtis
distancia_bray <- vegdist(datos, method = "bray")

# Paso 4: Realizar el clustering jerárquico con la matriz de distancia
cluster_bray <- hclust(distancia_bray)

# Paso 5: Crear el dendrograma
dendrograma <- as.dendrogram(cluster_bray)

# Paso 6: Mostrar el dendrograma con las altitudes como etiquetas
plot(dendrograma, main = "Dendrograma de Bray-Curtis", xlab = "Especies", ylab = "Distancia de Bray-Curtis")

# Paso 7: Etiquetar el dendrograma con las altitudes
labels(dendrograma) <- c("Altitud 231", "Altitud 355", "Altitud 443", "Altitud 544")




![sa1](https://github.com/Megasoma2222/INDICESDEDIVERSIDADBIOLOGIA/assets/137216764/91e1dc09-2a20-454e-9799-6f51368809da)
