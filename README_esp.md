# easyhunting

Easy hunting es una herramienta para facilitar el dia a dia de un "threat hunter" o analista de malware.

> [!IMPORTANT]
> easyHunting **NO SUBE** nada de informacion ni muestras a internet


### Forkeado de:
[ppt0/easyHunting](https://github.com/ppt0/easyhunting)

--- 
### Caracteristicas:
* Informe simple de una muestra:
    - *Firma peid*.
    -  Hashes basados en similitudes.
    - Descripcion de secciones
    - Firmas
    - Coincidencias [malapi](https://malapi.io/)
    - Coincidencias de fuentes de inteligencia (Virustotal, capa)
* 'Disassembly' de los primerosbytes para identificar si tiene o no un packer comercial comun, file infector o por si un 'trozo' de hex es una shellcode. (Para desensamblar una shellcode es imprescindible especificar de sc a x86 y de sc64 a x64).
* Obtiene reglas **yara**, **sigma** e **ids** desde un repositorio arbitrario (ejemplo. [este repo](https://github.com/Yara-Rules/rules)) y fuentes de inteligencia.
* Obtiene tecnicas MITRE utilizadas por la muestra. 
* Con las tecnicas MITRE obtenidas de diferentes fuentes de inteligenca se crea un JSON en  "mitre_navigator_reports" para importarlo en el framework de ataques MITRE.
* Obtiene **Muestras potencialmente similares** utilizando hash-es basados en similitud como; imphash, ssdeep, tlsh e icon shash. Ademas de otras caracteristicas como tamaño y metadatos. **NOTE**: Los hashes tlsh y ssdeep no estan disponibles para sistemas Windows.
* Obtiene informacion de amenazas sobre archivos, IPs, Dominios y URLs.
    - Informacion basica
    - Etiquetas de fuentes de inteligencia
    - Información relevante / interesante
    - ttps muestra tecnicas MITRE utilizadas en las muestras
    - Enclace a un informe completo
* Consultas a Virustotal para mejorar la busqueda de similares ([documentación](https://support.virustotal.com/hc/en-us/articles/360001385897-File-search-modifiers)). **NOTA**: Es necesaria una PRO api key.
* Muestra el malware mas reciente buscando con etiquetas.
* Descarga muestras de fuentes de inteligencia.
---
>[!IMPORTANT]
> Fuentes de inteligencia disponibles: *virustotal, bazaar, urlhaus, threatfox, alienvault, triage* y *tweetfeed*

### INSTALACION
1. Instala Python 3.13.2
2. Clona el repositorio
3. Instala los paquetes de Python 
    - Linux `python -m pip install -r linux-requirements.txt`
    - Windows `python -m pip install -r windows-requirements.txt`
4. [Configura las api-keys]
5. Ejecuta easyhunting.py

### Fichero de configuracion 
```
[apis]
virustotal = <vt-api-key>
triage = <triage-api-key>

[limits]
similar = 15
tags = 10
vtintelligence = 15
```

'Limits' Indica el numero de resultados para cada consulta. Por ejemplo, con tags = 10, la herramienta sólo mostrará los últimos 10 malware en cada fuente de intel con ese tag. 
>[!NOTE]
> Poner valores altos en "similar" puede ralentizar el tiempo de respuesta.



## INTEGRACIONES

#### Capa 3.2.0 integration
......




#### Integracion de reglas yara 

.......


## EJEMPLO DE USO
....