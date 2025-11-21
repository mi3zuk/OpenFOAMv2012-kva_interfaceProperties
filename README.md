# kva_interfaceProperties for OpenFOAMv2012
このライブラリの詳しい情報はコピー元を参照してください
[floquation/OF-kva_interfaceProperties](https://github.com/floquation/OF-kva_interfaceProperties)

# installation
```
git clone https://github.com/mi3zuk/OpenFOAMv2012-kva_interfaceProperties.git
cd OpenFOAMv2012-kva_interfaceProperties
```

パッケージの場合、OpenFOAMを起動
```
openfoam2012
```

```
chmod +x Allwmake Allwclean
```

`Allwmake`を実行すると、interfacePropertiesをコンパイルし、
interFoamとoverInterDyMFoamを再コンパイルします
(オリジナルを書き換える訳ではなく、`$FOAM_USER_APPBIN`に保存されます)
```
./Allwmake
```

使用法は本家と同じです

transportProperties↓
```
curvatureModel      vofsmooth; // normal; // If absent default: normal
vofsmoothCoeffs
{
    numSmoothingIterations 2; // If absent default: 2
}

surfaceTensionForceModel{
    densityWeighted         no; // If absent default: no (for my case I found density-weighting to _increase_ spurious currents)
}
```
v2012では、`densityWeighted`の有効化でspuriousCurrentsが大きく改善しました
