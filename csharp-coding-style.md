# E5R C# Coding Style

Guia de estilo de código E5R para C#

> Conheça os [Case Styles!][CASE-STYLES]

## Arquivos e classes

* Um arquivo por classe
* O nome da classe e do arquivo devem ser iguais
* Use [PascalCase][CASE-STYLES] tanto para nome do arquivo quanto da classe

Exemplo:
```c#
// file: MinhaClasse.cs
public class MinhaClasse {}
```

Para classes genéricas inclua o número de argumentos do tipo combinado ao nome do arquivo separados por um apóstrofo.

Exemplo:
```c#
// file: MinhaClasseGenerica`1.cs
public class MinhaClasseGenerica<T1> {}

// file: MinhaClasseGenerica`2.cs
public class MinhaClasseGenerica<T1, T2> {}
```


[CASE-STYLES]: https://betterprogramming.pub/string-case-styles-camel-pascal-snake-and-kebab-case-981407998841
