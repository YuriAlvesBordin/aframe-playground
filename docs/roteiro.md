# Roteiro de Apresentacao

Este documento serve como guia para a apresentacao oral do projeto. O tempo estimado total e de 12 a 15 minutos.

---

## 1. Introducao (2 min)

**Pontos a cobrir:**

- O que e o A-Frame e quem o criou (Mozilla, 2015)
- Proposta de valor: cenas 3D e WebXR usando apenas HTML
- Comparacao rapida com alternativas (Three.js puro, Babylon.js): A-Frame tem curva de aprendizado menor por ser declarativo
- Arquitetura Entity-Component System (ECS): entidades recebem comportamentos por componentes

**Trecho de codigo para mostrar:**

```html
<!-- Uma cena 3D funcional em 4 linhas -->
<a-scene>
  <a-box color="red" position="0 1 -3"></a-box>
  <a-camera></a-camera>
</a-scene>
```

---

## 2. Demo 1 — Primitivos 3D (3 min)

Abrir `cenas/primitivos.html`.

**Pontos a cobrir:**

- Mostrar o codigo-fonte ao lado da cena renderizada
- Cada tag HTML corresponde a uma geometria 3D
- Explicar o sistema de coordenadas: eixo X (horizontal), Y (vertical), Z (profundidade, negativo = para dentro da tela)
- Atributos basicos: `position`, `rotation`, `color`, `scale`

```html
<!-- Cubo posicionado 4 unidades a esquerda, 1 acima do chao, 5 a frente -->
<a-box position="-4 1 -5" color="#64ffda"
       animation="property:rotation; to:0 360 0; loop:true; dur:4000">
</a-box>
```

---

## 3. Demo 2 — Materiais PBR (3 min)

Abrir `cenas/materiais.html`.

**Pontos a cobrir:**

- O que e Physically Based Rendering (PBR): simulacao realista de como a luz interage com superficies
- `metalness`: 0 = nao metalico, 1 = metal puro
- `roughness`: 0 = superficie espelhada, 1 = superficie totalmente difusa
- `opacity` e `transparent`: controle de translucidez
- `emissive`: cor emitida independente de iluminacao (objetos que "brilham por conta propria")
- `wireframe`: renderizacao somente das arestas

```html
<!-- Material metalico espelhado -->
<a-sphere material="color:#cccccc; roughness:0; metalness:1"></a-sphere>

<!-- Material emissivo -->
<a-sphere material="color:#50fa7b; emissive:#50fa7b; emissiveIntensity:1"></a-sphere>
```

---

## 4. Demo 3 — Animacoes (3 min)

Abrir `cenas/animacoes.html`.

**Pontos a cobrir:**

- Animacoes sao definidas como atributos HTML, sem escrever JavaScript
- Parametros principais: `property`, `from`, `to`, `dur` (duracao em ms), `dir` (direction), `loop`, `easing`
- Qualquer propriedade numerica pode ser animada: posicao, rotacao, escala, cor, opacidade
- Multiplas animacoes paralelas: `animation__1`, `animation__2`, etc.
- Funcoes de easing disponiveis: `linear`, `easeInOutSine`, `easeInOutBounce`, `easeInOutCubic`

```html
<!-- Animacao de posicao com bounce -->
<a-sphere animation="property:position; from:0 0.5 -5; to:0 2 -5;
                    dir:alternate; loop:true; dur:1200; easing:easeInOutBounce">
</a-sphere>

<!-- Tres animacoes simultaneas no mesmo elemento -->
<a-torus-knot
  animation__1="property:rotation; to:0 360 0; loop:true; dur:4000"
  animation__2="property:scale; from:0.8 0.8 0.8; to:1.2 1.2 1.2; dir:alternate; loop:true; dur:2000"
  animation__3="property:material.emissiveIntensity; from:0; to:1; dir:alternate; loop:true; dur:1000">
</a-torus-knot>
```

---

## 5. Conclusao (2 min)

**Pontos a cobrir:**

- A-Frame abstrai a complexidade do WebGL/Three.js com uma API HTML familiar
- Funciona em desktop, mobile e headsets de Realidade Virtual sem alteracoes de codigo
- Ecossistema de componentes da comunidade: `aframe-extras`, `aframe-particle-system-component`, etc.
- Limitacoes: desempenho inferior a Three.js puro em cenas muito complexas; menos controle de baixo nivel

---

## Referencias para a Apresentacao

- https://aframe.io/docs/
- https://aframe.io/aframe-school/ (tutorial interativo oficial)
- https://github.com/aframevr/aframe
