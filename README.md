# info
## c't WIMage
[Projektseite](https://www.heise.de/hintergrund/c-t-WIMage-Stand-16-10-2017-3863074.html)

[Tuning: MS-Defender ExclusionProcess](https://www.heise.de/forum/c-t/Kommentare-zu-c-t-Artikeln/c-t-WIMage/Tuning-MS-Defender-ExclusionProcess/posting-38144340/show/#posting_38144340)

## Keepass 2
### URL-Overrides
```
cmd://cmd /c "cmdkey /generic:TERMSRV/{URL:RMVSCM} /user:{USERNAME} /pass:{PASSWORD} && mstsc /v:{URL:RMVSCM} && timeout /t 5 /nobreak && cmdkey /delete:TERMSRV/{URL:RMVSCM}"
cmd://"c:\Program Files\uvnc bvba\UltraVNC\vncviewer.exe" "{URL:RMVSCM}"
```
