# Emscripten

## Build

```
mkdir build && cd build
emcmake cmake ..
emmake make
```

## Link

```
em++ -flto -O3 -fno-rtti -fno-exceptions *.o ../../../include/textscreen/include/libtextscreen.a -o index.html -sUSE_SDL=2 -sASYNCIFY -sASYNCIFY_ONLY=@funcs.txt -sASYNCIFY_IGNORE_INDIRECT -sENVIRONMENT=web --preload-file FILE0000.GLB --preload-file FILE0001.GLB --preload-file SETUP.INI --preload-file TimGM6mb.sf2 --closure 1
```
