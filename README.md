# Trucos para bibliotecas
Documentación para la solución de problemas que encontramos en la vida bibliotecaria

# Scripts para la terminal de Windows

## Quitar espacios y reemplazarlos por guiones bajos
```winbatch
cmd /e:on /v:on /c "for %f in ("* *.txt") do (set "n=%~nxf" & set "n=!n: =_!" & ren "%~ff" "!n!" )" 
```

# Pequeños scripts en python

## Transformando los nombres de un archivo con acentos y eñes a ASCII

```python
import os
import unidecode #para esto habrá que hacer pip install unidecode

src_dir = #aquí se pone la dirección de la carpeta
for file_name in os.listdir(src_dir): 
    normalized = unidecode.unidecode(file_name)
    #print(file_name, normalized)
    os.rename(os.path.join(src_dir,file_name), os.path.join(src_dir, normalized))
```

## Agregando un prefijo a los nombres de archivo
```python
os.chdir("")  #aquí se pone la dirección de la carpeta
os.getcwd()

from glob import glob
pre = "2011_" #<- aquí se agrega el prefijo que se quiera poner
[os.rename(f, "{}{}".format(pre, f)) for f in glob("*.pdf")]
```

# Programas útiles

## Text Mining

### Orange

1. Instalar Anaconda para tu sistema operativo https://www.anaconda.com/download/
2. Instalar orange3-text: https://github.com/biolab/orange3-text


a) En el Anaconda Prompt primero añadir "add conda-forge" a tus canalees:

    conda config --add channels conda-forge

b) Después se instala orange text

    conda install orange3-text

c) Luego se abre el programa con:

    python -m Orange.canvas
