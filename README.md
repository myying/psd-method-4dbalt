# PSD Method Tutorial: Baltic Sea Altimetry Intercomparison

Jupyter notebook tutorial comparing the power spectral density (PSD) of sea level anomaly (SLA) / sea surface height anomaly (SSHA) from four altimetry products over the Baltic Sea, 29 March - 9 July 2023:

- **FFSAR** — Fully-Focused SAR altimetry, optimally-interpolated (OI) SLA with geostrophic velocities (IGG, University of Bonn), L4
- **RADS** — conventional radar altimetry, OI SLA with geostrophic velocities (IGG, University of Bonn), L4
- **SL TAC** — Copernicus Marine Service (CMEMS) DUACS all-satellite merged L4 SLA product, European Seas
- **SWOT** — SWOT KaRIn L3 SSHA, 1-day cal/val phase (AVISO/CNES/CLS DUACS)

The notebook computes along-track power spectra for each product, plots the mean PSD alongside reference `k^-5` and `k^-11/3` power laws, and compares time series at a common location, to illustrate how effective resolution differs between conventional altimetry, fully-focused SAR altimetry, and SWOT wide-swath altimetry.

## Notebook

[`L3and4_Baltic_Edito.ipynb`](L3and4_Baltic_Edito.ipynb)

## Running the tutorial

### On EDITO Datalab

1. Launch the **jupyter-notebook** service from the [EDITO Datalab catalog](https://datalab.dive.edito.eu/).
2. Clone this repository, or upload `L3and4_Baltic_Edito.ipynb`, into the running notebook server.
3. Open the notebook and run all cells. The first code cell installs `netCDF4` and `geopy`; the second downloads and extracts the tutorial dataset (`4dbalt.tar.gz`, ~900 MB) from Zenodo automatically.

### Locally

```bash
pip install numpy matplotlib netCDF4 scipy geopy jupyter
jupyter notebook L3and4_Baltic_Edito.ipynb
```

Running the setup cell will download and extract the data into a local `4dbalt/` folder. Alternatively, download the archive manually from the Zenodo record (see below) and extract it next to the notebook:

```bash
tar xzf 4dbalt.tar.gz
```

## Data

The tutorial data (`4dbalt.tar.gz`) is archived on Zenodo: **[DOI: 10.5281/zenodo.22771211](https://doi.org/10.5281/zenodo.22771211)** *(draft — link resolves once the record is published)*.

It contains four folders of daily/per-pass NetCDF files covering 29 March - 9 July 2023 over the Baltic Sea:

| Folder | Product | Level | Files |
|---|---|---|---|
| `FFSAR_0323to0723/` | Fully-Focused SAR altimetry OI SLA + geostrophic velocities | L4 | 103 |
| `RADS_0323to0723/` | Conventional altimetry (RADS) OI SLA + geostrophic velocities | L4 | 103 |
| `SLTAC_0323to0723/` | CMEMS DUACS all-satellite merged SLA (SL TAC) | L4 | 103 |
| `SWOT_1dayCalval/` | SWOT KaRIn L3 SSHA, 1-day cal/val phase | L3 | 99 |

This is a research-use subset assembled for this tutorial; see `zenodo_metadata.md` for full provenance and licensing of each source product. Users of the data must cite the original data providers (IGG Bonn, CMEMS, and AVISO/CNES/CLS) as noted there.

## Repository contents

- `L3and4_Baltic_Edito.ipynb` — the tutorial notebook
- `zenodo_metadata.md` — metadata/description used for the Zenodo data deposit
- `README.md` — this file

## License

Data: see `zenodo_metadata.md` for per-source licensing of each altimetry product.
