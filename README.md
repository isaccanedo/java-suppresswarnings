# 1. Visão Geral
Neste tutorial rápido, veremos como usar a anotação @SuppressWarnings.

# 2. Anotação @SuppressWarnings
As mensagens de aviso do compilador geralmente são úteis. Às vezes, os avisos podem ser barulhentos.

Especialmente quando não podemos ou não queremos abordá-los:

```
public class Machine {
    private List versions;

    public void addVersion(String version) {
        versions.add(version);
    }
}
```

O compilador emitirá um aviso sobre este método. Ele avisará que estamos usando uma coleção de tipo bruto. Se não quisermos corrigir o aviso, podemos suprimi-lo com a anotação @SuppressWarnings.

Essa anotação nos permite dizer quais tipos de avisos ignorar. Embora os tipos de aviso possam variar de acordo com o fornecedor do compilador, os dois mais comuns são reprovação e desmarcado.

deprecation diz ao compilador para ignorar quando estamos usando um método ou tipo obsoleto.

desmarcado diz ao compilador para ignorar quando estamos usando tipos brutos.

Portanto, em nosso exemplo acima, podemos suprimir o aviso associado ao nosso uso de tipo bruto:

```
public class Machine {
    private List versions;

    @SuppressWarnings("unchecked")
    // or
    @SuppressWarnings({"unchecked"})
    public void addVersion(String version) {
        versions.add(version);
    }
}
```

Para suprimir uma lista de vários avisos, definimos uma matriz String contendo a lista de avisos correspondente:

```
@SuppressWarnings({"unchecked", "deprecated"})
```

# 3. Conclusão
Neste guia, vimos como podemos usar a anotação @SuppressWarnings em Java.