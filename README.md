

Demonstração interativa da biblioteca [A-Frame](https://aframe.io) para criação de cenas 3D no navegador via WebXR. Desenvolvido como projeto acadêmico para a disciplina de Computação Gráfica.

<img width="1069" height="624" alt="image" src="https://github.com/user-attachments/assets/440e4cf8-cecd-4682-aaca-70ff51e62035" />

## Estrutura do Projeto

```
aframe-demo-faculdade/
|
+-- index.html              # Pagina inicial com navegacao entre as demos
|
+-- cenas/
|   +-- demo1.html          # Demo 1 — Primitivos geometricos com morphing
|   +-- demo2.html          # Demo 2 — Modelo atomico com iluminacao dinamica
|   +-- demo3.html          # Demo 3 — Importacao de modelos 3D externos
|   +-- demo1-ar.html       # Demo 1 em AR (marcador Hiro)
|   +-- demo2-ar.html       # Demo 2 em AR (marcador Hiro)
|   +-- demo3-ar.html       # Demo 3 em AR (marcador Hiro)
|
+-- docs/
|   +-- roteiro.md          # Roteiro para apresentacao oral
|
+-- .gitignore
```

---

## Como Executar

Nao ha dependencias ou etapas de build. Sirva os arquivos localmente:

```bash
# Python
python -m http.server 8080

# Node.js
npx serve .
```

Acesse `http://localhost:8080` no navegador.

> **Nota:** abrir via `file://` pode causar erros de CORS em alguns navegadores. Recomenda-se usar um servidor local.

---

## Demos

### Demo 1 — Primitivos em Morphing

Exibe os primitivos geometricos nativos do A-Frame (`<a-box>`, `<a-sphere>`, `<a-cylinder>`, `<a-cone>`, `<a-torus>`, `<a-torus-knot>`, `<a-icosahedron>`, entre outros) com transicoes automaticas entre formas a cada 2,8 segundos. Cada troca aplica um material PBR aleatorio, variando `roughness`, `metalness`, `opacity`, `emissive` e `wireframe`.

![Demo 1 - Primitivos em Morphing](demo_gifs/demo1.gif)

### Demo 2 — Modelo Atomico

Simulacao de um atomo com nucleo central e eletrons orbitando em planos distribuidos tridimensionalmente. A quantidade de eletrons e configuravel em tempo real via slider (1 a 10). Cada eletron emite luz pontual colorida e transiciona continuamente entre cores via interpolacao HSL, iluminando o nucleo e os eletrons vizinhos.

![Demo 2 - Modelo Atomico](demo_gifs/demo2.gif)

### Demo 3 — Importacao de Modelo 3D

Permite carregar um arquivo `.glb`, `.gltf` ou `.obj` do sistema de arquivos local via drag-and-drop ou seletor de arquivo. O modelo e centralizado e escalonado automaticamente. A cena oferece controles de orbita estilo Blender: arrastar para orbitar, scroll para zoom e botao direito para pan. Suporte completo a toque em dispositivos moveis.

<img width="1069" height="624" alt="image" src="https://github.com/user-attachments/assets/fd97c5be-6ed0-4449-85db-4983722de5d0" />

---

## Modo AR

Cada demo possui uma versão em Realidade Aumentada acessível pelo botão **Modo AR** na cena. A AR utiliza a biblioteca [AR.js](https://ar-js-org.github.io/AR.js/) com rastreamento por marcador **Hiro**.

Imprima ou exiba o marcador abaixo na tela para usar o modo AR:

<p align="center">
  <img
    src="https://raw.githubusercontent.com/AR-js-org/AR.js/master/data/images/hiro.png"
    alt="Marcador Hiro — AR.js"
    width="220"
    height="220"
  />
  <br>
  <em>Marcador Hiro — aponte a câmera para este padrão para ativar a AR</em>
</p>
