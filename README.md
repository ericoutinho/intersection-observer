# Intersection Observer

1. Criando um novo observer

```javascript
const observer = new IntersectionObserver( entries => {
    entries.forEach( entry => {
        entry.target.classList.toggle("show", entry.isIntersecting)
    })
}, {options})

elements.forEach (element => {
    observer.observe(element)
})
```

2. Definindo o ponto de ativação dos elementos

```javascript
const observer = new IntersectionObserver( entries => {
    entries.forEach( entry => {
        entry.target.classList.toggle("show", entry.isIntersecting)
    })
}, {
    threshold: 1
})
```

A opção _threshold_ deve possuir um valor entre 0 e 1, que vai difinir o percentual e exibição de elemento na tela que ativará o callback. Threshold 0.5 o elemento estará 50% visível, threshold 1, 100%.

3. Definido margens (offset) para ativação. Valor positivo

```javascript
const observer = new IntersectionObserver( entries => {
    entries.forEach( entry => {
        entry.target.classList.toggle("show", entry.isIntersecting)
    })
}, {
    rootMargin: "100px",
})
```

4. Define o container do observador.

```javascript
    {
        root: document.querySelector(element)
    }
```

5. Executando o observador apenas uma vez

```javascript
const observer = new IntersectionObserver( entrie => {
    entries.forEach( entry => {
        entry.target.classList.toggle("show", entry.isIntersecting)
    })

    if (entry.isIntersecting) observer.unobserve(entry.target)
}, {
    threshold: 1
})
```
