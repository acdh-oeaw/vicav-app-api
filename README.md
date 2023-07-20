# API for the VICAV website

Extract OpenAPI YAML from insomnia
Needs `yq` (think `jq` for YAML). E. g. `scoop install yq`


Windows:
```powershell
yq eval .contents $(ls .\.insomnia\ApiSpec\spc_*.yml) > openapi.yaml
(cat .\openapi.yaml) -replace '\\/', '/' | yq -o json > .\openapi.json
```

Unix-like:
```bash (tested on a mac)
yq eval .contents $(ls .\.insomnia\ApiSpec\spc_*.yml) > openapi.yaml
cat ./openapi.yaml | sed "s/\\\\\//\//g" | yq -o json > ./openapi.json
```