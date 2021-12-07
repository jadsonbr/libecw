libecw
======
     
## Primeiro remova o gdal se já estiver instalado

```bash
sudo apt remove gdal-bin gdal-data libgdal20
sudo apt autoremove
sudo apt install libpng-dev unzip
```

## Faça o download do código ou clone do repositório

- Por download
```bash
wget https://github.com/jadsonbr/libecw/archive/master.zip
unzip master.zip -d ecw && cd ecw/libecw-master
 ```
 
 - Por clone
 ```bash
 git clone https://github.com/jadsonbr/libecw.git
 cd libecw
 ```
 
 ## Configurando e instalando o libecw
 
 ```bash
sudo ./configure  CFLAGS="-O0" CXXFLAGS="-O0"  --enable-shared --enable-static --prefix=/usr
```

```bash
sudo make
```

```bash
sudo make install
```

## Download GDAL v2.3 Source (ex. 2.3.1)

```bash
wget http://download.osgeo.org/gdal/2.3.1/gdal-2.3.1.tar.gz
```

- Para download de outra versão acesse: [http://download.osgeo.org/gdal/](http://download.osgeo.org/gdal/)

## Construir GDAL com suporte ECW

- Descompacte o arquivo baixado

```bash
unzip gdal-2.3.1.zip
cd gdal-2.3.1
```

- Configure o GDAL

```bash
sudo ./configure --with-ecw=/usr
```

- Rodar `make` e `make install`
```bash
sudo make
```

```bash
sudo make install
```

## Verifique se funciona

```bash
gdalinfo --formats | grep ECW
```

## Exemplo de utilização

```bash
gdal_translate --config ECW_LARGE_OK YES -of ECW orto.tif ortomosaico_ecw.ecw
```
