## Instalar paquetes
install.packages("readxl")

## Activar libreria
library(readxl)

## Abrir base de datos en excel
read_xlsx("Excel_base_hypoglycemia.xlsx")

## Conocer la naturaleza de las variables en las bases de datos
str(base_hypoglycemia)

## Cambiar la naturaleza de las variables
base_hypoglycemia$`Sexo del RN`=factor(base_hypoglycemia$`Sexo del RN`,levels = c(2,1),labels = c("Mujer","Varón"))
base_hypoglycemia$`Tipo de Parto`=factor(base_hypoglycemia$`Tipo de Parto`,levels = c(1,2),labels = c("Vaginal","Cesárea"))
base_hypoglycemia$`Uso de Drogas`=factor(base_hypoglycemia$`Uso de Drogas`,levels = c(2,1),labels = c("No","Si"))
base_hypoglycemia$`Inducción del parto`=factor(base_hypoglycemia$`Inducción del parto`,levels = c(2,1),labels = c("No","Si"))
base_hypoglycemia$`Hijo de Madre Diabética`=factor(base_hypoglycemia$`Hijo de Madre Diabética`,levels = c(2,1),labels = c("No","Si"))
base_hypoglycemia$RCIU=factor(base_hypoglycemia$RCIU,levels = c(2,1),labels = c("No","Si"))
base_hypoglycemia$`Madre THE`=factor(base_hypoglycemia$`Madre THE`,levels = c(2,1),labels = c("No","Si"))
base_hypoglycemia$SALAM=factor(base_hypoglycemia$SALAM,levels = c(2,1),labels = c("No","Si"))
base_hypoglycemia$`Estrés perinatal`=factor(base_hypoglycemia$`Estrés perinatal`,levels = c(2,1),labels = c("No","Si"))
base_hypoglycemia$`Hipoglucemia neonatal`=factor(base_hypoglycemia$`Hipoglucemia neonatal`,levels = c(1,2), labels = c("si","no"))
str(base_hypoglycemia)

## Visualizar la base de datos
View(base_hypoglycemia)

## Medidas de resumen
summary(base_hypoglycemia)

## Medidas de resumen específicos
table(base_hypoglycemia$`Edad Gestacional`)
table(base_hypoglycemia$`Peso del RN`)
table(base_hypoglycemia$`Sexo del RN`)

## OBSERVAR GRÁFICOS CIRCULARES
table(base_hypoglycemia$`Sexo del RN`)
frecuencia_sexoRN<-table(base_hypoglycemia$`Sexo del RN`)
pie(frecuencia_sexoRN, 
    labels = c("Mujer","Varón"),
    col = c("blue","green"),
    main="Sexo del Recién nacido")

## Histogramas
install.packages("Hmisc")
library (Hmisc)
hist.data.frame(base_hypoglycemia)
hist(base_hypoglycemia$`Edad Gestacional`, 
     main = "Edad Gestacional",
     xlab="Edad")

## Diagrama de barras
table(base_hypoglycemia$`Sexo del RN`,base_hypoglycemia$`Hijo de Madre Diabética`)
barra_imagen=table(base_hypoglycemia$`Sexo del RN`,base_hypoglycemia$`Hijo de Madre Diabética`)

colnames(barra_imagen)=c("Mujer","Varón")
rownames(barra_imagen)=c("Si","No")    
barplot(barra_imagen,legend=TRUE, main = "Hijo de madre diabética según sexo del RN")

# Diagrama de barras mejorado
barplot(barra_imagen,
        main="Hijo de madre diabética según sexo del RN",
        col=c("darkblue","lightblue"),
        space=.5, 
        xlab="Sexo",
        legend=TRUE,
        fill=c("darkblue","lightblue"))

## DIAGRAMA DE CAJAS
boxplot(base_hypoglycemia$`Peso del RN`,
        col="lightblue",
        main="Edad gestacional y Peso del RN", 
        xlab="Edad")

### MEDIDAS DE TENDENCIA CENTRAL Y DISPERSIÓN: MEDIA Y DESVIACIÓN ESTÁNDAR
mean(base_hypoglycemia$`Peso del RN`)
sd(base_hypoglycemia$`Peso del RN`)


#CREANDO TABLAS DE CSV PARA LA PRESENTACIÓN
library(tableone)
attach(base_hypoglycemia)
tabla1=CreateTableOne(data=base_hypoglycemia); tabla1
tabla1=print(tabla1,showAllLevels=T)
tabla1=CreateTableOne(data = base_hypoglycemia,
                      strata="Hipoglucemia neonatal"); tabla1

tabla2=print(tabla1,showAllLevels=T); tabla2
write.csv(tabla2,file ="tablabivariada_hipoglucemia.csv")

