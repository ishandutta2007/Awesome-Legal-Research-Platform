# Awesome-Legal-Research-Platform

git add assets/banner.svg ;git commit -m "banner"; git push origin (git branch --show-current)

$repo_name = [string]::IsNullOrEmpty($repo_name) ? (Get-Item .).Name : $repo_name

git pull

if (Test-Path "node_modules") { rm node_modules/* }

if (Test-Path "scratch") { rm scratch/* }

rm *.py

rm *.ps1

rm *.txt



#Commit new files one by one

git status --porcelain | ForEach-Object { $f = ($_ -split '\s+', 2)[1]; if ($f) { git add $f; git commit -m "Chg: $f" } }; git push origin (git branch --show-current)



#Commit updated files one by one

git diff --name-only | ForEach-Object { git commit -m "Update $_" $_ }

git push origin (git branch --show-current)



if (Test-Path "$loops_path\sheet_outputs\$real_repo_name.txt") { mv "$loops_path\sheet_outputs\$real_repo_name.txt" "$loops_path\sheet_outputs\_$real_repo_name.txt" }

(Get-Content -Path "../$repo_name/README.md") -replace "GitHub Stars", "GitHub_Stars" | Set-Content -Path "../$repo_name/README.md"

(Get-Content -Path "../$repo_name/README.md") -replace "Github Stars", "GitHub_Stars" | Set-Content -Path "../$repo_name/README.md"

(Get-Content -Path "../$repo_name/README.md") -replace "Stars Badge", "Stars_Badge" | Set-Content -Path "../$repo_name/README.md"

(Get-Content -Path "../$repo_name/README.md") -replace "Star Badge", "Stars_Badge" | Set-Content -Path "../$repo_name/README.md"

(Get-Content -Path "../$repo_name/README.md") -replace "Stars Count", "Stars_Count" | Set-Content -Path "../$repo_name/README.md"

(Get-Content -Path "../$repo_name/README.md") -replace "Star Count", "Stars_Count" | Set-Content -Path "../$repo_name/README.md"

git add README.md ;git add assets ;git commit -m "final readme";git -c http.sslVerify=false push;git status

if (-not (Test-Path "assets\social-preview.gif")) { svg2gif -s 1.0 }

git add assets/social-preview.gif ;git commit -m "social-preview"; git push origin (git branch --show-current)

gh-browse-or-reload
