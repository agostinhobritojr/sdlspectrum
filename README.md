# spectrosdl - Visualizador de Espectro de Áudio

Este projeto implementa um visualizador de espectro de áudio em C++ utilizando as bibliotecas:

- SDL2
- SDL2_mixer
- FFTW3

> 📦 O objetivo é capturar dados de áudio, aplicar FFT e exibir visualmente o espectro em tempo real.

---

## ✅ Funcionalidades

- Leitura e reprodução de arquivos MP3
- Cálculo do espectro de áudio usando FFT
- Visualização gráfica do espectro (via SDL2)

---

## ⚙️ Requisitos

Antes de compilar, certifique-se de ter as seguintes bibliotecas instaladas:

- SDL2
- SDL2_mixer
- FFTW3
- (Opcional) OpenGL, se o código exigir

---

## 🪟 Instalação no Windows

### Opção 1: Usando MSYS2 (Recomendado)

1. Baixe e instale o MSYS2: https://www.msys2.org/
2. Abra o terminal **MSYS2 MINGW64**
3. Instale as dependências:

```bash
pacman -Syu
pacman -S mingw-w64-x86_64-gcc \
           mingw-w64-x86_64-SDL2 \
           mingw-w64-x86_64-SDL2_mixer \
           mingw-w64-x86_64-fftw
```

4. Compile o código:

```bash
g++ spectrosdl.cpp -o spectrosdl.exe -lSDL2 -lSDL2_mixer -lfftw3 -std=c++11
```

5. Execute:

```bash
./spectrosdl.exe arquivo.mp3
```

---

### Opção 2: Usando vcpkg + g++

1. Instale o [vcpkg](https://github.com/microsoft/vcpkg)
2. Instale as bibliotecas necessárias:

```bash
vcpkg install sdl2 sdl2-mixer fftw3
```

3. Compile com os diretórios apropriados:

```bash
g++ spectrosdl.cpp -I<path-to-vcpkg>/installed/x64-windows/include \
                   -L<path-to-vcpkg>/installed/x64-windows/lib \
                   -lSDL2 -lSDL2_mixer -lfftw3 -std=c++11 -o spectrosdl.exe
```

---

## 🐧 Instalação no Linux (Ubuntu/Debian)

1. Instale as dependências:

```bash
sudo apt update
sudo apt install build-essential libsdl2-dev libsdl2-mixer-dev libfftw3-dev
```

2. Compile o projeto:

```bash
g++ spectrosdl.cpp -o spectrosdl -lSDL2 -lSDL2_mixer -lfftw3 -std=c++11
```

3. Execute:

```bash
./spectrosdl arquivo.mp3
```

---

## ⚠️ Observações

- Se o código depender de OpenGL, adicione:
  - Linux: `-lGL -lGLU -lGLEW`
  - Windows: `-lopengl32`
- Verifique se há arquivos `.mp3` no mesmo diretório do executável (caso o programa dependa deles)
- Em erros de linkagem, use `pkg-config` para encontrar os nomes corretos das bibliotecas:

```bash
pkg-config --cflags --libs sdl2 SDL2_mixer fftw3
```

---

## 🚧 Desenvolvimento Futuro

- [ ] Adicionar `Makefile` e/ou `CMakeLists.txt`
- [ ] Interface interativa para selecionar arquivos de áudio
- [ ] Modo espectrograma (tempo x frequência)
- [ ] Exportar espectro em PNG ou vídeo

---

## 📄 Licença

Este projeto é de uso livre para fins educacionais e de pesquisa. Sinta-se à vontade para contribuir!

---

## 🙋‍♂️ Autor

**Agostinho Brito**

---

> Para dúvidas, melhorias ou contribuições, abra uma *issue* ou envie um *pull request*.
