# aframe-demo-faculdade

Projeto acadêmico de demonstração da biblioteca [A-Frame](https://aframe.io) para criação de cenas 3D interativas no navegador via WebXR.

**Autor:** Yuri Alves Bordin

---

## Sobre o A-Frame

A-Frame é uma biblioteca web de código aberto desenvolvida pela Mozilla que permite construir experiências 3D e de Realidade Virtual (WebVR/WebXR) usando HTML declarativo. Internamente, ela é construída sobre o [Three.js](https://threejs.org) e segue o padrão arquitetural **Entity-Component System (ECS)**, onde cada elemento da cena é uma entidade que recebe comportamentos por meio de componentes.

O diferencial da biblioteca é permitir que cenas 3D completas sejam descritas com marcação HTML pura, sem necessidade de pipeline de build, bundler ou configuração de ambiente:

```html
<a-scene>
  <a-box color="#4CC3D9" position="0 1 -3"></a-box>
  <a-camera></a-camera>
</a-scene>
```

---

## Estrutura do Projeto

```
aframe-demo-faculdade/
|
+-- index.html              # Pagina inicial com navegacao entre as demos
|
+-- cenas/
|   +-- primitivos.html     # Demo 1 — Primitivos geometricos nativos
|   +-- materiais.html      # Demo 2 — Sistema de materiais PBR
|   +-- animacoes.html      # Demo 3 — Animacoes declarativas
|
+-- docs/
|   +-- roteiro.md          # Roteiro para apresentacao oral
|
+-- .gitignore
```

---

## Como Executar

Nao ha dependencias ou etapas de build. Os arquivos podem ser abertos diretamente no navegador ou servidos localmente:

```bash
# Servidor local com Python
python -m http.server 8080

# Servidor local com Node.js
npx serve .
```

Depois acesse `http://localhost:8080` no navegador.

> **Nota:** alguns recursos (como carregamento de texturas externas) exigem um servidor HTTP. Abrir via `file://` pode causar erros de CORS.

---

## Demos

### Demo 1 — Primitivos 3D

Demonstra os elementos geometricos nativos do A-Frame: `<a-box>`, `<a-sphere>`, `<a-cylinder>`, `<a-cone>`, `<a-torus>` e `<a-plane>`. Cada primitivo aceita atributos de posicao, rotacao, escala e cor diretamente no HTML.

### Demo 2 — Materiais e Texturas

Explora o sistema de renderizacao baseado em fisica (PBR) do A-Frame por meio do atributo `material`. Propriedades demonstradas: `roughness`, `metalness`, `opacity`, `transparent`, `emissive`, `emissiveIntensity` e `wireframe`.

### Demo 3 — Animacoes Declarativas

Ilustra o sistema de animacao do A-Frame via atributo `animation`. Propriedades animadas: `position`, `rotation`, `scale` e `material.color`. Tambem demonstra multiplas animacoes paralelas (`animation__1`, `animation__2`, ...) e diferentes funcoes de easing.

---

## Controles de Navegacao

| Acao | Controle |
|---|---|
| Girar a camera | Clicar e arrastar |
| Movimentar | Teclas `W` `A` `S` `D` |
| Ativar modo VR (se disponivel) | Botao no canto inferior direito |

---

## Compatibilidade

Testado nos navegadores modernos com suporte a WebGL 2.0:

- Google Chrome 120+
- Mozilla Firefox 120+
- Microsoft Edge 120+
- Safari 17+ (suporte parcial a WebXR)

---

<sub>Projeto academico — uso educacional.</sub>
