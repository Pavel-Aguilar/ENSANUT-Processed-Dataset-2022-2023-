# ENSANUT-Processed-Dataset-2022-2023-
Database integrated with real information taken from 8 surveys with public data on Mexican youth. I focused only on ages 10 to 14, since certain data are only available in that age range. The database is created from:

"Cuestionario de salud de adolescentes (10 a 19 años)" ENSANUT Continua - 2023.

"Cuestionario de salud de adolescentes (10 a 19 años)" ENSANUT Continua Guanajuato - 2022.

"Cuestionario de salud de adolescentes (10 a 19 años)" ENSANUT Continua Nuevo León - 2022.

"Cuestionario de salud de adolescentes (10 a 19 años)" ENSANUT Continua - 2022.

"Cuestionario de actividad física - Niños (10 a 14 años)" ENSANUT Continua - 2023.

"Cuestionario de actividad física - Niños (10 a 14 años)" ENSANUT Continua Guanajuato - 2022.

"Cuestionario de actividad física - Niños (10 a 14 años)" ENSANUT Continua Nuevo León - 2022.

"Cuestionario de actividad física - Niños (10 a 14 años)" ENSANUT Continua - 2022.

Most columns of the same type were joined (for example, to create "violencia_fisica", "límites" and "violencia_psic"), and many variables were binarized to slightly reduce the strong data imbalance. All were remapped for better interpretation:

Binary columns "fuma", "fuma_e-cig" (vape), "alcohol" "diabetes", "hta", "colesterol", "trigliceridos", "dificultades_", "depresiones_", nutritional and food-related, "autoherido_suicidio" and "pensar_suicidio", "límites" (which refers to the limits set by the person exercising upbringing), "violencia_fisica", "violencia_psic":

0 - Absence of the condition
1 - Presence of the condition

Column "sexo":

1 - Male
2 - Female

Columns "frecuencia_ansiedad", "frecuencia_tristeza":

How often do you feel very anxious, nervous or worried?

0 - Never
1 - Weekly or daily.
2 - Monthly or several times a year.

Column "tiempo_transporte", which deals with the time spent traveling from home to school on a typical day.

0 - Less than 10 minutes.
2 - Between 10 and 30 minutes.
3 - Between 30 min and 1 hour.
4 - Between 1 and 2 hours.
5 - Between 2 and 3 hours
6 - More than 3 hours.

Column "tipo_transporte", which deals with the type of transport used for the longest journey from home to school:

1 - Walk.
2 - Bicycle (pedaled by oneself).
3 - Bicycle (pedaled by someone else).
4 - Bus, train, tram, subway, collective taxi, motorized boat.
5 - Car, motorcycle, moped.
6 - Other.

Column "cantidad_equipos_ultaño", which deals with how many teams, individual sports or physical activities they participated in at a competitive level or very frequently, such as after-school programs or school teams, during the last 12 months.

0 - None
1 - 1 activity.
2 - 2 activities.
3 - 3 activities.
4 - 4 or more activities.

Columns "frente_pantalla", "frente_videojuevos", "frente_internet", which deal with the hours spent in front of a TV, playing video games and browsing the internet (like on a cell phone).

0 - Nothing.
1 - Less than 1 hour.
2 - 1 to 2 hours.
3 - 3 to 4 hours.
4 - 5 to 6 hours.
5 - 7 to 8 hours.
6 - 9 or more hours.

Columns "dormir" (sleep time) and "despertar" (wake up time), which deal with the schedules they keep:

1 - Before 6.
2 - Between 6 and 7.
3 - Between 7 and 8.
4 - Between 8 and 9.
5 - Between 9 and 10.
6 - Between 10 and 11.
7 - After 11.

Column "act_dias_semana", which deals with all the time they spent running, walking fast, cycling, dancing, skating, skateboarding, swimming, playing soccer and basketball, in a week.

0 - 0 days.
1 - 1 day.
2 - 2 days.
3 - 3 days.
4 - 4 days.
5 - 5 days.
6 - 6 days.
7 - 7 days."

===================================================================================

Base de datos que se integró con información real tomada de 8 encuestas con datos públicos en jóvenes mexicanos. Me concentré solo en edades de 10 a 14 años, ya que ciertos datos solo están disponibles en ese rango de edad. La base de datos es creada a partir de:

-Cuestionario de salud de adolescentes (10 a 19 años) ENSANUT Continua - 2023.

-Cuestionario de salud de adolescentes (10 a 19 años) ENSANUT Continua Guanajuato - 2022.

-Cuestionario de salud de adolescentes (10 a 19 años) ENSANUT Continua Nuevo León - 2022.

-Cuestionario de salud de adolescentes (10 a 19 años) ENSANUT Continua - 2022.

-Cuestionario de actividad física - Niños (10 a 14 años) ENSANUT Continua - 2023.

-Cuestionario de actividad física - Niños (10 a 14 años) ENSANUT Continua Guanajuato - 2022.

-Cuestionario de actividad física - Niños (10 a 14 años) ENSANUT Continua Nuevo León - 2022.

-Cuestionario de actividad física - Niños (10 a 14 años) ENSANUT Continua - 2022.


La mayoría de las columnas del mismo tipo se unieron (por ejemplo para crear violencia física, límites y violencia psicológica), de igual forma se binarizaron muchas variables para aminorar un poco el fuerte desbalanceo en los datos. Todas se remapearon para su mejor interpretación:

Columnas  binarias "fuma", "fuma_e-cig" (vape), "alcohol" "diabetes", "hta", "colesterol", "trigliceridos", "dificultades_", "depresiones_", nutricionales y alimenticios, "autoherido_suicidio" y "pensar_suicidio", "límites" (que habla acerca de los límites por quien ejerce la crianza), "violencia_fisica", "violencia_psic":

0 - Ausencia de la condición
1 - Presencia de la condición

Columna "sexo":

1 - Hombre
2 - Mujer

Columnas "frecuencia_ansiedad", "frecuencia_tristeza":
Con qué frecuencia te muestras muy ansioso/a, nervioso/a o preocupado/a. 

0 - Nunca
1 - Semanalmente o diariamente.
2 - Mensualmente o varias veces al año.

Columna "tiempo_transporte", que trata del tiempo que pasa transportándose de la casa a la escuela en un día típico:

0 - Menos de 10 minutos.
2 - Entre 10  y 30 minutos.
3 - Entre 30 min y 1 hora.
4 - Entre 1 y 2 horas.
5 - Entre 2 y 3 horas
6 - Más de 3 horas.

Columna "tipo_transporte", que trata del tipo de transporte que utilizan en el trayecto mas largo de la casa a la escuela:

1 - Caminata.
2 - Bicicleta (pedaleada por si mismo).
3 - Bicicleta (pedaleada por alguien mas).
4 - Autobús, tren, tranvía, metro, colectivo, bote motorizado.
5 - Automóvil, motocicleta, motoneta.
6 - Otro.


Columna "cantidad_equipos_ultaño", que trata de cuántos equipos , deportes individuales o actividades físicas participaron a un nivel competitivo o con mucha frecuencia, como programas fuera de la escuela o equipos de la escuela, durante los últimos 12 meses.

0 - Ninguno
1 - 1 actividad.
2 - 2 actividades.
3 - 3 actividades.
4 - 4 o más actividades.


Columnas "frente_pantalla", "frente_videojuevos", "frente_internet", que tratan de las horas que pasan frente a una tv, jugando videojuegos y navegando en internet (como el celular).

0 - Nada.
1 - Menos de 1 hora.
2 - 1 a 2 horas.
3 - 3 a 4 horas.
4 - 5 a 6 horas.
5 - 7 a 8 horas.
6 - 9 o más horas.


Columnas "dormir" y "despertar", que tratan de los horarios que llevan:

1 - Antes de las 6.
2 - Entre 6 y 7.
3 - Entre 7 y 8.
4 - Entre 8 y 9.
5 - Entre 9 y 10.
6 - Entre 10 y 11.
7 - Después de las 11.


Columna "act_dias_semana", que trata de todo el tiempo que utilizaron para correr, caminar rápidamente, andar en bicicleta, bailar, patinar, andar en patineta, nadar, jugar futbol y basquetbol, en una semana:

0 - 0 días.
1 - 1 día.
2 - 2 días.
3 - 3 días.
4 - 4 días.
5 - 5 días.
6 - 6 días.
7 - 7 días.


