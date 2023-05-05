# API for the VICAV website

Extract OpenAPI YAML from insomnia
```powershell
yq eval .contents $(ls .\.insomnia\ApiSpec\spc_*.yml) > openapi.yaml
(cat .\openapi.yaml) -replace '\\/', '/' | yq -o json > .\openapi.json
```
Needs `yq` (think `jq` for YAML). E. g. `scoop install yq`