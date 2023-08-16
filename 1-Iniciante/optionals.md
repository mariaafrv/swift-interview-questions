# O que é um opcional e qual problema eles resolvem?

![](/resources/optionals.png)

É importante verificar se essa variável possui valor antes de utilizá-lo em algum trecho de código. Para isso, temos 4 opções:

## Force unwrapping

Como o nome mesmo já diz, o force unwrapping força um valor a ser desembrulhado, é a forma explicita de extrair um valor de um optional.

~~~swift
func exemploFuncao(optionalVar: String) {
    print(optinalVar)
}

var nilVar: String? = nil
exemploFuncao(optinalVar: nilVar!)
~~~

O force unwrapping pode ser utilizado quando variáveis não podem ser nulas, no entanto, é necessário muito cuidado ao utilizá-lo, pois códigos como o acima resultaria em um erro, afinal o valor da variável é nulo.

## Binding opcional

### if let
O optional binding garante que um trecho de código será executado apenas se uma determinada variável não for nula.

~~~swift
var optinalVar: String? = nil

if let unwrappedVar = optionalVar {
    //Se o valor da variável 'optionalVar' não for nulo, ele será atribuido á variável 'unwrappedVar' e o código dentro da closure será executado.
}
~~~

### guard let
O guard let valida se uma variável contém valor e caso seja nula, executa um trecho de código .

~~~swift
func checkVar(optionalVar: String?) -> Bool {
    guard let unwrappedVar = optionalVar else {
        return false
    }
}
~~~

## Optional chaining
Encadeamento opcional é usado quando alguns atributos de objetos podem ser nulos.

~~~swift
var optionalChaining = firstVar?.secondVar?.thirdVar
~~~
A varíavel 'optionalChaining' será do tipo opcional, e ela receberá um valor apenas se os objetos não forem nil, caso algum tenha valor nil, a variável também terá valor nil.
