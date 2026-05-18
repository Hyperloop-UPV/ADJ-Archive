# ADJ Archive

Historical store of compacted [ADJ](https://github.com/Hyperloop-UPV/adj) snapshots.

Every time a commit on the `adj` repository passes the validation workflow, the
full ADJ configuration is compacted into a single JSON file and pushed here.


<p align="center">
  <a href="https://hyperloopupv.com/#/">
    <img src="https://user-images.githubusercontent.com/58437819/204690695-1fd3cac0-85f5-49c4-99e9-cb20ca89429f.png"
         alt="Logo Hyperloop UPV"
         width="550">
  </a>
</p>



## Layout

```
storage/
└── commit-<sha>.json   # one file per upstream commit
```

- `<sha>` is the **full 40-character commit hash** of the originating commit in
  the [`adj`](https://github.com/Hyperloop-UPV/adj) repository.
- Each file is a self-contained, minified JSON mirroring the directory
  structure of the source repo (boards, packets, measurements, orders, etc.).

## Usage

To fetch the ADJ snapshot for a given upstream commit:

```bash
curl -O https://raw.githubusercontent.com/Hyperloop-UPV/ADJ-Archive/main/storage/commit-<sha>.json
```

## Publishing

Files are written automatically by the `ADJ Validator` workflow in
`Hyperloop-UPV/adj`. Do not commit by hand.

Used by Control Station

