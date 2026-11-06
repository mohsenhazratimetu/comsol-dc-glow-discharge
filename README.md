# DC argon glow discharge in COMSOL

Two COMSOL Java API exports from my work on DC glow discharge modelling. The models couple charged-particle transport and electrostatics to an external circuit. They include electron energy and argon metastable transport.

| Model | What to inspect |
| --- | --- |
| `ArgonGlowDischarge1D.java` | One-dimensional discharge with a transient study and a circuit-resistance sweep. Inspect the discharge current and voltage and the axial density profiles. |
| `ArgonGlowDischarge2D.java` | Axisymmetric discharge with a transient study. Inspect the spatial ion density and axial electric field. |

## Build and open the models

Use COMSOL Multiphysics 6.4 and its command-line tools. Keep both `.mphbin` files in the repository root for the 1D geometry. Run these commands from that directory.

```sh
comsol compile "$PWD/ArgonGlowDischarge1D.java"
comsol batch -inputfile "$PWD/ArgonGlowDischarge1D.class" -outputfile "$PWD/argon-glow-1d.mph"

comsol compile "$PWD/ArgonGlowDischarge2D.java"
comsol batch -inputfile "$PWD/ArgonGlowDischarge2D.class" -outputfile "$PWD/argon-glow-2d.mph"
```

Open the resulting MPH file in COMSOL and compute the study of interest. The exports contain model definitions and study settings. The 1D export sets the circuit resistance to 500 Ω in its parameter block. The source file name contains the older `5kOhm` label.

Both Java files were compiled against the COMSOL 6.4 API. [COMSOL batch and compile commands](https://doc.comsol.com/6.4/doc/com.comsol.help.comsol/comsol_ref_running.38.33.html)
