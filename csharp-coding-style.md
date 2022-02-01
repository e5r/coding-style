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

## Quebra de linha

Em muitos momentos precisamos _não ter uma linha de código muito extensa_, os motivos são vários e podemos
discutí-los ainda. Mas por hora queremos definir o seguinte:

* Sempre que possível utilize no máximo *80* caracteres por linha. Ex:
```
[abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz]
```
* Quando precisar de mais, procure não extrapolar os **100** caracteres por linha. Ex:
```
[abcdefghijklmnopqrstuvwxyz0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789abcdefghijklmnopqrstuvwxyz]
```
* Mas nunca ultrapasse os **120** caracteres por linha de código. Ex:
Ex:
```
[0123456789abcdefghijklmnopqrstuvwxyz0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789abcdefghijklmnopqrstuvwxyz0123456789]
```
Exemplo no Visual Studio Code com réguas configuradas:
![](https://user-images.githubusercontent.com/3629320/152056931-2cfe774d-8136-431f-8de1-ac10925c3a02.png)

Para conseguir seguir essas diretrizes de limite máximo de caracteres por linha, por vezes você encontrará
algumas dificuldades. Então abaixo temos as regras de como proceder em cada caso.

### Em instruções IF

```c#
// Ao invés disso
if (operacaoBoleanaEntre != variaveis && combinadasCom == operadoresLogicos && eQuandoSua <> instrucaoForMuitoGrande && estrapolarQuantidade < permitidaDeCaracteres && porUma > linhaUnica)
{
    // ...
}

// Faça isso
if (operacaoBoleanaEntre != variaveis 
    && combinadasCom == operadoresLogicos 
    && eQuandoSua <> instrucaoForMuitoGrande 
    && estrapolarQuantidade < permitidaDeCaracteres 
    && porUma > linhaUnica)
{
    // 1. Deixamos apenas uma operação na linha imediatamente a instrução IF
    // 2. Quebramos a linha antes do operador lógico (&&), indentamos 1 nível
    // 3. Deixamos apenas uma instrução por linha iniciando sempre no operador lógico
    // 4. Fechamos o parêntese ")" junto a última linha
    // 5. Quebramos novamente para usar o braço "{", e voltamos 1 nível na indentação
}
```

### Assinatura de métodos e construtores

```c#
// Ao invés disso
private TipoResultadoDaSuaFuncao MeuMetodoComMuitosParametros(VocePodeTerVarios parametrosComTipos, BemEspecificos quePodemOcupar, PorSuaVezMuitos caracteresDeCodigoParaSerem, DescritosNaSua assinaturaDeFuncao)
{
}

private static SePorAcasoSomenteADescricaoDoSeuTipoDeRetorno JuntoAoNomeDaFuncaoForSemConsiderarOsParametrosForMuitoGrande()
{
}

private static SePorAcasoSomenteADescricaoDoSeuTipoDeRetorno JuntoAoNomeDaFuncaoForSemConsiderarOsParametrosForMuitoGrande(VocePodeTerVarios parametrosComTipos, BemEspecificos quePodemOcupar, PorSuaVezMuitos caracteresDeCodigoParaSerem, DescritosNaSua assinaturaDeFuncao)
{
}

// Faça isso
private TipoResultadoDaSuaFuncao MeuMetodoComMuitosParametros(
    VocePodeTerVarios parametrosComTipos,
    BemEspecificos quePodemOcupar,
    PorSuaVezMuitos caracteresDeCodigoParaSerem,
    DescritosNaSua assinaturaDeFuncao)
{
    // 1. Quebramos a linha logo após a abertura do parêntese "("
    // 2. Indentamos 1 nível, e deixamos apenas um parâmetro por linha finalizando com a vírgula
    // 3. Fechamos o parêntese ")" junto a última linha
    // 4. Quebramos novamente para usar o braço "{", e voltamos 1 nível na indentação
}

private static SePorAcasoSomenteADescricaoDoSeuTipoDeRetorno 
    JuntoAoNomeDaFuncaoForSemConsiderarOsParametrosForMuitoGrande()
{
    // 1. Quebramos a linha logo após o tipo de retorno
    // 2. Indentamos 1 nível, e deixamos apenas o nome do método com seus parênteses
    // 3. Quebramos a linha novamente após os parênteses para usar o braço "{", e voltamos 1 nível na indentação
}

private static SePorAcasoSomenteADescricaoDoSeuTipoDeRetorno
    JuntoAoNomeDaFuncaoForSemConsiderarOsParametrosForMuitoGrande(
        VocePodeTerVarios parametrosComTipos,
        BemEspecificos quePodemOcupar,
        PorSuaVezMuitos caracteresDeCodigoParaSerem,
        DescritosNaSua assinaturaDeFuncao)
{
    // 1. Quebramos a linha logo após o tipo de retorno
    // 2. Indentamos 1 nível, e deixamos apenas o nome do método
    // 3. Quebramos a linha logo após a abertura do parêntese "("
    // 4. Indentamos novamente 1 nível, e deixamos apenas um parâmetro por linha finalizando com a vírgula
    // 5. Fechamos o parêntese ")" junto a última linha
    // 6. Quebramos novamente para usar o braço "{", e voltamos 2 níveis na indentação
}
```

[CASE-STYLES]: https://betterprogramming.pub/string-case-styles-camel-pascal-snake-and-kebab-case-981407998841
