# aframe-demo-faculdade

Demonstração interativa da biblioteca [A-Frame](https://aframe.io) para criação de cenas 3D no navegador via WebXR. Desenvolvido como projeto acadêmico para a disciplina de Computação Gráfica.

<img width="1069" height="624" alt="image" src="https://github.com/user-attachments/assets/440e4cf8-cecd-4682-aaca-70ff51e62035" />

## Estrutura do Projeto

```
aframe-demo-faculdade/
|
+-- index.html              # Pagina inicial com navegacao entre as demos
|
+-- cenas/
|   +-- primitivos.html     # Demo 1 — Primitivos geometricos com morphing
|   +-- materiais.html      # Demo 2 — Modelo atomico com iluminacao dinamica
|   +-- animacoes.html      # Demo 3 — Importacao de modelos 3D externos
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

(DemoGif 1)

### Demo 2 — Modelo Atomico

Simulacao de um atomo com nucleo central e eletrons orbitando em planos distribuidos tridimensionalmente. A quantidade de eletrons e configuravel em tempo real via slider (1 a 10). Cada eletron emite luz pontual colorida e transiciona continuamente entre cores via interpolacao HSL, iluminando o nucleo e os eletrons vizinhos.

(DemoGif 2)

### Demo 3 — Importacao de Modelo 3D

Permite carregar um arquivo `.glb`, `.gltf` ou `.obj` do sistema de arquivos local via drag-and-drop ou seletor de arquivo. O modelo e centralizado e escalonado automaticamente. A cena oferece controles de orbita estilo Blender: arrastar para orbitar, scroll para zoom e botao direito para pan. Suporte completo a toque em dispositivos moveis.

<img width="1069" height="624" alt="image" src="https://github.com/user-attachments/assets/fd97c5be-6ed0-4449-85db-4983722de5d0" />
