Please follow the [official tutorial](https://www.cp2k.org/howto:static_calculation) to understand the sections/keywords used here. 

Instead of using `&COORD` section, atomic coordinates can also be written in an additional file (e.g., `coord.xyz`) and be included via 

```text
&TOPOLOGY
    COORD_FILE_FORMAT XYZ
    COORD_FILE_NAME coord.xyz
&END TOPOLOGY
```