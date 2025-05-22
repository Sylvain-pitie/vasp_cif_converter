# VASP-CIF Converter

A Python script to convert between CIF and VASP POSCAR/CONTCAR files, including automatic space group detection and symmetry application.

---

## Features

- Convert CIF files to VASP POSCAR format
- Convert POSCAR/CONTCAR files to symmetrized CIF files
- Automatic space group detection and application
- Support for custom symmetry precision (`symprec`)
- Command-line interface with flexible arguments

---

## Requirements

- Python 3.6+
- [pymatgen](https://pymatgen.org/)

Install dependencies:
```bash
pip install pymatgen
```

---

## Usage

```bash
python vasp_cif_converter <input_file> [output_cif_file] [symprec]
```

### Arguments:
- `<input_file>`: Path to a CIF (`.cif`) or VASP file (`POSCAR`/`CONTCAR`)
- `[output_cif_file]` *(optional)*: Name of the output CIF file when converting from POSCAR/CONTCAR
- `[symprec]` *(optional)*: Symmetry precision (default is `0.01`)

---

## Examples

Convert a CIF file to a VASP POSCAR:
```bash
python vasp_cif_converter example.cif
```

Convert a POSCAR file to a symmetrized CIF (with default symprec):
```bash
python vasp_cif_converter POSCAR
```

Convert a POSCAR file to a symmetrized CIF with custom output name:
```bash
python vasp_cif_converter POSCAR my_structure.cif
```

Convert with a custom symmetry tolerance:
```bash
python vasp_cif_converter POSCAR my_structure.cif 0.001
```

---

## Notes

- If no output filename is specified, the output CIF will be named `<input_file>.symmetrized.cif`
- Only files recognized by `pymatgen` as valid POSCAR/CIF are supported

