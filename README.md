# kva_interfaceProperties for OpenFOAMv2012
For more information about this library, see the source.
[floquation/OF-kva_interfaceProperties](https://github.com/floquation/OF-kva_interfaceProperties)

# installation
```
git clone https://github.com/mi3zuk/OpenFOAMv2012-kva_interfaceProperties.git
cd OpenFOAMv2012-kva_interfaceProperties
```

For packages, start OpenFOAM
```
openfoam2012
```

```
chmod +x Allwmake Allwclean
```

Running `Allwmake` will compile interface properties and recompile
interFoam and overInterDyMFoam.
(The originals will not be overwritten, and will be saved in `$FOAM_USER_APPBIN`.)
```
./Allwmake
```

Usage is the same as the original

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
