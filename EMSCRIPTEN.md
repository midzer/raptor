# Emscripten

## Build

```
mkdir build && cd build
emcmake cmake ..
emmake make
```

## Link

```
emcc -flto -O3 *.o ../../../include/textscreen/include/libtextscreen.a -o index.html -sUSE_SDL=2 -sASYNCIFY -sENVIRONMENT=web --preload-file FILE0000.GLB --preload-file FILE0001.GLB --preload-file SETUP.INI --preload-file TimGM6mb.sf2 --closure 1
```
