Se presentan a continuación

1.  El autor del primer microrrelato:

```
PREFIX mcr:   <https://w3id.org/def/microrrelatos#>

select distinct ?autor{
    mcr:microrrelato_1 mcr:esObraArtisticaCreadaPor ?autor
}
``` 

2.  El nombre y los apellidos del autor del primer microrrelato:

```
PREFIX mcr:   <https://w3id.org/def/microrrelatos#>

select distinct ?nombre ?apellidos{
    mcr:microrrelato_1 mcr:esObraArtisticaCreadaPor ?autor .
    ?autor mcr:nombreDePila ?nombre .
    ?autor mcr:apellidos ?apellidos .
}
```

El resultado es el siguiente:

```
nombre  apellidos

"Ana"^^<http://www.w3.org/2001/XMLSchema#string> "Martínez Castillo"^^<http://www.w3.org/2001/XMLSchema#string>
``` 

3. El título de los microrrelatos publicados por Ana Martínez Castillo:

```
PREFIX mcr:   <https://w3id.org/def/microrrelatos#>

select distinct ?titulo{
    ?microrrelato mcr:esObraArtisticaCreadaPor ?autor .
    ?label rdfs:label "Ana Martínez Castillo"@es .
    ?microrrelato rdfs:label ?titulo
}
```  
