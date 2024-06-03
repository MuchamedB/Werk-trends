# Kwadratische Vergelijking Oplosser

Dit project bevat een PowerShell-script dat kwadratische vergelijkingen van de vorm \(ax^2 + bx + c = 0\) oplost. Het script berekent de discriminant en bepaalt of de vergelijking geen, één, of twee reële oplossingen heeft.

## Functies

- Berekening van de discriminant
- Detectie van het aantal reële oplossingen
- Weergave van de oplossingen

## Vereisten

- PowerShell 5.0 of later

## Gebruik

1. Clone deze repository naar je lokale machine:
    ```sh
    git clone https://github.com/jouw-gebruikersnaam/kwadratische-vergelijking-oplosser.git
    ```

2. Navigeer naar de directory van het project:
    ```sh
    cd kwadratische-vergelijking-oplosser
    ```

3. Voer het script uit in PowerShell:
    ```sh
    .\Solve-wiskundeprobleem.ps1
    ```

## Script Uitleg

Het script definieert een functie `Solve-QuadraticEquation` die drie parameters accepteert: `a`, `b`, en `c`. Deze parameters zijn de coëfficiënten van de kwadratische vergelijking.

### Voorbeeld

```powershell
function Solve-QuadraticEquation {
    param (
        [double]$a,
        [double]$b,
        [double]$c
    )

    # Bereken de discriminant
    $discriminant = $b * $b - 4 * $a * $c

    if ($discriminant -lt 0) {
        Write-Output "De vergelijking heeft geen reële oplossingen."
    }
    elseif ($discriminant -eq 0) {
        $x = -$b / (2 * $a)
        Write-Output "De vergelijking heeft één oplossing: x = $x"
    }
    else {
        $x1 = (-$b + [math]::Sqrt($discriminant)) / (2 * $a)
        $x2 = (-$b - [math]::Sqrt($discriminant)) / (2 * $a)
        Write-Output "De vergelijking heeft twee oplossingen: x1 = $x1 en x2 = $x2"
    }
}

# Voorbeeld gebruik van de functie
$a = 1
$b = -3
$c = 2

Solve-QuadraticEquation -a $a -b $b -c $c
