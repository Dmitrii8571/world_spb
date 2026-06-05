# Заголовок 1 уровня(самый большой)
## Заголовок 2
### Заголовок 3
#### Заголовок 4

*Курсив* или _курсив_
**Жирный** или __жирный
***Жирный курсив*** или __жирный курсив__
~~Зачеркнутый~~

- Элемент 1
- Элемент 2
    - Вложенный элемент(2 пробела или табуляция)

    1. Первый
    2. Второй
    3. Третий


    [текст ссылки](https://www.magnific.com/ru/free-ai-image/view-beautiful-persian-domestic-cat_299691835.htm#fromView=keyword&page=1&position=1&uuid=c88af923-3b9f-43c2-aedc-d88d08bab92c&query=%D0%9C%D0%B8%D0%BB%D1%8B%D0%B5+%D0%BA%D0%BE%D1%82%D0%B8%D0%BA%D0%B8)

    ![Альтернативный текст](https://www.magnific.com/ru/free-ai-image/view-beautiful-persian-domestic-cat_299691835.htm#fromView=keyword&page=1&position=1&uuid=c88af923-3b9f-43c2-aedc-d88d08bab92c&query=%D0%9C%D0%B8%D0%BB%D1%8B%D0%B5+%D0%BA%D0%BE%D1%82%D0%B8%D0%BA%D0%B8)


    `Write-Host`

    ```bash
<#
.SYNOPSIS
    Автоматическая сортировка фйлов в папке загрузка.
.Description
    Создаёт подпапки по типу и перемещает в них содержимое
    Безопсно для повторного запуска
.NOTES
    Версия 0.01
#>

[CmdletBiding()]

param(
    [switch]$DryRum
)

$DownloadPath = "$env:USERROFILE\Downloads"

$Categories = @{
    "Imafes" = @("*.jpg", "*.jpeg")
    "Documents" = @("*.doc", "*.docx", "*.pdf", "*.txt")
    "Archives" = @("*zip", "*rar")
    "Installers" = @("*.exe", "*bat", "*.ps1")
    "Media" = @("*.mp3", "*avi")
}
Write_Host "Начало сортировки" -ForgroundCol Cyanor
Write_Host "Папка: $DownloadPath" -ForgroundColor Gray

foreach ($Category in $Categories[$Category]) {
    $Files = Get-ChildItem -Path $DownloadPath -Filter $Pattern -File -ErrorAction SilentlyContinue 
   $TargetFolder = Join-Path $DownloadPath $Categories
   if (-not(Test-Path $TargetFolder)) {
   New-Item -Path $TargetFolder -ItemType Directory -Force | Out-Null
   Write-Host "Соданна папка" $Category" -ForgroundCol DarkGray

   foreach ($Pattern in $Categories [$Category]){
  

    foreach ($File in $Files) {
    if ($File.DirectoreyName -eq $TargetFolder){ continue }

    $Dest = Join-Path $TargetFolder $File.Name 

    $Dest = Join-Path $TargetFolder $File.Name

    }

    if (Test-Path $Dest) {
        $Base= [System.IO.Path]::GetFileNameWithoutExtension($File.Name)
        [System.IO.Path]::GetFiltExtension($File.Name)

        $Timestamp = Get-Date -Format "yyyyyMMdd_HHmmss"
        $DryRum = Join-Path $TargetFolder "${Base}_$Timestamp$Exit"
        Write-Host "Дубликат имени: $($File.Name) -> переименован" -ForegroundColor Yellow
        
        }

        if ($DryRum) {
            Write-Host "[Прогноз] $($File.Name)" -> $Category\" -ForegroundColor Yellow
            
    
        } else {
            try {
            Move-Item -Path $File.FullName -Destination $Dest -Force -ErrorAction Stop

            Write-Host "OK $($File.Name) ->$Category\" -ForegroundColor DarkGreen

            }
            catch{
                Write-Warning "Не удалось переместить $($File.Name):$($_.Exception.Mwssege)"
         }
            }
        

  


Write-Host "Сортировка завершина" -ForegroundColor Cyan
    ```

> это циата
> она может занимать несколько строк


---

***

| Имя | Возраст | Город |
|-----|---------|-------|
Антон | 20      | Санкт-Петербург|
| Иван | 25 | Москва |
