# casm-utilities-primify
This is a [casm-utilties plugin](https://github.com/goirijo/casm-utilities/tree/0.4.X_transition#preparing-plugins-for-compilation).
It takes the path to a structure (VASP format), converts it to its primitive form, and saves the primitive structure to a new file.

## Example
The conventional fcc cell for Ni is

    Ni_fcc_conventional
    1.0
    3.50950044 0.00000000 0.00000000
    0.00000000 3.50950044 0.00000000
    0.00000000 0.00000000 3.50950044
    Ni
    4
    Direct
    0.00000000 0.00000000 0.00000000
    0.50000000 0.50000000 0.00000000
    0.50000000 0.00000000 0.50000000
    0.00000000 0.50000000 0.50000000

If stored to a file named `fcc_conventional.vasp` we can create the primitive fcc cell with the following command:
```bash
casmutils primify --superstructure fcc_conventional.vasp
```

Will output the primitive structure to the screen

    1.00000000
    0.00000000 1.75475022 1.75475022
    1.75475022 0.00000000 1.75475022
    1.75475022 1.75475022 0.00000000
    Ni 
    1 
    Direct
    0.00000000 0.00000000 0.00000000 Ni

To save the output to a file pipe it or use the `--output` option:
```bash
casmutils primify --superstructure fcc_conventional.vasp --output fcc_primitive.vasp
```
