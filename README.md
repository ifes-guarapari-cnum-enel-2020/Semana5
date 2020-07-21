# Semana5
Atividades Pedagógicas Não Presenciais

## Método da bisseção
O método da bisseção explora o fato de que uma função contínua deverá ter um zero em algum intervalo de dois pontos em que a imagem alterna entre um valor positivo e negativo. Assim, a ideia para aproximar o zero da função é tomar, como primeira aproximação, o ponto médio desse intervalo, e, sucessivamente, para os intervalos entre esses pontos médios, até encontrar o valor próximo ao zero.

https://www.ufrgs.br/reamat/CalculoNumerico/livro-py/sdeduv.html

Nesse exercício, o objetivo é identificar os zeros da função de terceiro grau ![formula](https://render.githubusercontent.com/render/math?math=f(x)=x^3-9x+3), sabendo que eles estão entre os intervalos vistos graficamente e com um erro aproximado na terceira casa.
```julia
f(x) = x^3 - 9*x + 3

error = 10^-3

function bisection(a,b)
 x = (a+b)/2
 while abs(f(x)) > error
  if f(a)*f(x) > 0
   a = x
  else
   b = x
  end
  x = (a+b)/2
 end
 return x
end

r = bisection(-4,-3)
println(r)

r = bisection(0,1)
println(r)

r = bisection(2,3)
println(r)
```

Observa-se na solução que as divisões são realizadas próximas ao valor esperado, melhorando a precisão da resposta a cada repetição, encerrando o loop ao chegar no valor próximo ao erro.
