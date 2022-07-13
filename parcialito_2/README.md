# Teoría de Algoritmos II (75.30)

### 1.<sup>er</sup> Parcialito Domiciliario – 29/04/2022 - Fecha de Entrega: 20/05/2022
---

> Aclaraciones: Cada ejercicio dice al final del mismo la cantidad de puntos que otorga por hacerse completamente bien (en total, 10). Se deben obtener al menos 5 puntos para aprobar, y se deben aprobar al menos 3 de los parcialitos para aprobar/regularizar la cursada. Para la fecha de entregar, enviar un mail a mbuchwald@fi.uba.ar con un pdf con la resolución, con nombre P2 - PADRON.pdf. Pueden incluir todo el material adicional que les parezca relevante (desde código hasta gráficos).
---
Nuevamente, considerando [esta red que representa las conexiones de diferentes países por los vuelos](https://www.google.com/url?sa=D&q=https://drive.google.com/file/d/1bZ5xauNeqo4i3oV-qeQQrk-1DbQmF9a8/view%3Fusp%3Dsharing&ust=1652449320000000&usg=AOvVaw23iBFNMdzm6igRBcmFVuSY&hl=es) (directos) realizados entre ellos, responder las siguientes preguntas. A los fines de estos ejercicios, se puede obviar la última columna del archivo csv.

1. [Notebook ejercicio 1](notebooks/ejercicio_1.ipynb)
> a. Obtener una visualización de las comunidades presentes en dicha red (indicando el algoritmo utilizado). 

![Comunidades](/media/world_communities_louvain.png)

> b. Considerando lo que respondiste en el parcialito 1 (ejercicio 2):      
>  * Si mencionaste que había homofilia, ¿corresponde por el mismo tipo que mencionaste anteriormente? ¿por qué?    
>  * Si mencionaste que no había homofilia (o bien no realizaste el ejercicio), ¿qué tipo de homofilia se puede ver presente?

Es el mimsmo tipo de homofilia que se mencionó en el parcialito 1. En el parcialito anterior lo había graficado con gephi, sin cononcimientos de los algoritmos para detección de comunidades. Ahora, utilizando el algoritmo de Louvain, podemos observar que hay comunidades por continente o proximidad geográfica. En amarillo se observan países Africanos, en azul países Europeos, en verde países de America y en violeta países de Oceanía y Asia. 

> c. Obtener los nodos correspondientes a una de las subredes (con al menos 20% de los nodos), y realizar una visualización de las sub-comunidades presentes.

![Sub-Comunidades](/media/sub_graph_communities_louvain.png)

Observamos que siguen habiendo communidades por ubicación geografica. La comunidad más grande que había era la de Asia-Oceanía, con este nuevo subgrafo observamos comunidades también por ubicación gegrafica. Principalmente entre Oceanía y Asia, y luego dentro de Asia entre las diferentes regiones del continente. 

A grandes rasgos: 

* Asia Central (violeta)
* Asia Occidental y Asia del Sur (azul)
* Sudeste asiático (con mezclas de el este de Melanesia y Micronesia) (verde)
* Australasia y Polinesia (Amarillo)

**[3 puntos]**

1. [Notebook ejercicio 2](notebooks/ejercicio_2.ipynb)
> a. Calcular los motifs de hasta 5 nodos de la subred definida en el punto 1.c.

Calculo de los motifs del subgrafo 1.c:

[ 6767   2160  35791  29980   1972  52722  21829   6045 105359 307703 82477 231338 154949 259346   2809  36856 353316  50223 219685   1730 31693  72409 224009 167290  14795 188349  14597  65421  11833 ]

 
> b. Calcular el promedio y desvío estandar de los motifs de una red de baseline. Calcular el significant profile de la red, y hacer un gráfico.

![Sub-Comunidades](/media/significant_profile.png)

> c. Intentar dar con una explicación del resultado obtenido en el punto anterior [+1 punto].

Claramente hay varios subgrafos que se mantienen poco semejante a lo esperado. Hay varios subgrafos que estan sobrerepresentados, sobretodo el 8, 28 y 29. Son los subgrafos que estan muy conectados entre todos, lo cual tiene sentido si estamos hablando de una red de vuelos (donde sería deseable poder llegar desde un mismo nodo a varios países sin hacer combinaciones). 

**[4 puntos]** *(sin contar 2.c)*

3. [Notebook ejercicio 3](notebooks/ejercicio_3.ipynb)
   
    Detectar los roles en dicha red utilizando el algoritmo RolX, explicando el resultado obtenido.

![Sub-Comunidades](/media/roles.png)

Roles       | Promedio Grados | Promedio Centralidad | Países
------------|-----------------|---------------------|---------
Amarillo     | 57.25              |0.012975895509131832  | Austria, Cote d'Ivoire, Cyprus, Czech Republic, Denmark, Egypt, Greece, Hungary, India, Italy, Malaysia, Malta, Norway, Poland, Russia, Sweden, Switzerland, Thailand, Ukraine, United States
Azul      | 9.524193548387096  |0.0009625121173228564 | Afghanistan, American Samoa, Anguilla, Antigua and Barbuda, Armenia, Aruba, Bahamas, Barbados, Belize, Benin, Bermuda, Bhutan, Bolivia, Botswana, British Virgin Islands, Brunei, Burkina Faso, Burma, Burundi, Cambodia, Cameroon, Cayman Islands, Central African Republic, Chad, Christmas Island, Cocos (Keeling) Islands, Comoros, Congo (Brazzaville), Congo (Kinshasa), Cook Islands, Djibouti, Dominica, East Timor, Ecuador, El Salvador, Equatorial Guinea, Eritrea, Falkland Islands, Faroe Islands, Fiji, French Guiana, French Polynesia, Gabon, Gambia, Gibraltar, Greenland, Grenada, Guadeloupe, Guam, Guatemala, Guernsey, Guinea, Guinea-Bissau, Guyana, Haiti, Honduras, Isle of Man, Jamaica, Jersey, Kiribati, Kyrgyzstan, Laos, Lesotho, Liberia, Libya, Macau, Madagascar, Malawi, Mali, Marshall Islands, Martinique, Mauritania, Mayotte, Mongolia, Montserrat, Mozambique, Myanmar, Namibia, Nauru, Nepal, Netherlands Antilles, New Caledonia, New Zealand, Nicaragua, Niger, Niue, Norfolk Island, North Korea, Northern Mariana Islands, Palau, Papua New Guinea, Paraguay, Peru, Puerto Rico, Reunion, Rwanda, Saint Helena, Saint Kitts and Nevis, Saint Lucia, Saint Pierre and Miquelon, Saint Vincent and the Grenadines, Samoa, Sao Tome and Principe, Sierra Leone, Somalia, South Sudan, Sudan, Suriname, Swaziland, Syria, Tajikistan, Togo, Tonga, Trinidad and Tobago, Turkmenistan, Turks and Caicos Islands, Tuvalu, Uruguay, Vanuatu, Virgin Islands, Western Sahara, Yemen, Zambia, Zimbabwe
Naranja      | 33.50684931506849  |0.005884932162109333 | Albania, Algeria, Angola, Argentina, Australia, Azerbaijan, Bahrain, Bangladesh, Belarus, Bosnia and Herzegovina, Brazil, Bulgaria, Canada, Cape Verde, Chile, China, Colombia, Costa Rica, Croatia, Cuba, Dominican Republic, Estonia, Ethiopia, Finland, Georgia, Ghana, Hong Kong, Iceland, Indonesia, Iran, Iraq, Ireland, Israel, Japan, Jordan, Kazakhstan, Kenya, Kuwait, Latvia, Lebanon, Lithuania, Luxembourg, Macedonia, Maldives, Mauritius, Mexico, Moldova, Montenegro, Morocco, Nigeria, Oman, Pakistan, Panama, Philippines, Portugal, Romania, Saudi Arabia, Senegal, Serbia, Seychelles, Singapore, Slovakia, Slovenia, South Africa, South Korea, Sri Lanka, Taiwan, Tanzania, Tunisia, Uganda, Uzbekistan, Venezuela, Vietnam
Gris      | 4.0                |9.572187625632562e-05 | Micronesia, Solomon Islands, Wallis and Futuna
Verde      | 102.22222222222223 |0.04992226785242998 | Belgium, France, Germany, Netherlands, Qatar, Spain, Turkey, United Arab Emirates, United Kingdom




Viendo estos resultados, claramente se nota que el role esta muy ligado a el grado y la centralidad del nodo, con lo cual se podría decir que los nodos azules y grises probablemente representen nodos perfericos, en los cuales haya que hacer varias combinaciones de vuelos para llegar a ellos. Los naranjas representan nodos un poco más accesibles, pero no tan importantes dentro de la red, y por ultimo los amarillos y verdes representen nodos con muchas aristas de los cuales se necesten muy pocas combinaciones para llegar a ellos.
   
**[3 puntos]**