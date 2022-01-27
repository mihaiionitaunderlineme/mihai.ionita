<br>
<br>Arhiva cod lucru Template Overleaf, setari: Compiler: XeLaTeX, TeX Live version: 2020<br>
[instructiune_lucru_template.zip](https://github.com/mihaiionitaunderlineme/mihai.ionita/files/7953035/instructiune_lucru_template.zip)
<br>PDF-ul rezultat din compilarea codului pe platfora Overleaf<br>
[instructiune_lucru_template.pdf](https://github.com/mihaiionitaunderlineme/mihai.ionita/files/7953045/instructiune_lucru_template.pdf)
<br>Comentarii la cudul sursa<br>
<br><br>
Preambulul documentului
```LaTeX
\documentclass[11pt,a4paper]{article}
```
Permite setarea unui font caracteristic - de interes a fost fontul Arial narrow. Necesita compilarea cu XeTeX sau LuaTex. Fosierul arialn.ttf a fost incarcat in mod specific. Se poate folosi astfel orice font. 
```LaTeX
\usepackage{fontspec}
\setmainfont{arialn.ttf}
```
Rezolvarea problemelor cu textul din tabele. 
Fara cod avem ca rezultat
![tabel1](https://user-images.githubusercontent.com/16071968/151432253-96c01101-9995-4e2a-952a-97396c4bd46c.PNG)
iar cu: 
```LaTeX
\usepackage{makecell} 
\setcellgapes{5pt}
```
![tabel2](https://user-images.githubusercontent.com/16071968/151431501-e85505e0-f7d5-4907-89a8-a3006b281e32.PNG)
Ca cerinta specifica aveam trecerea de la Nivelul I - Capitolul 4, Nivelul II - Subcapitolul 4,1 catre nivelul III care trebuia sa contina enumerarea pe baza de litere. 
Fara cod avem ca rezultat
![tabel3](https://user-images.githubusercontent.com/16071968/151435190-2806572b-d6ea-4e3d-a2c0-758b483500bd.PNG)
iar cu: 
```LaTeX
\usepackage[shortlabels]{enumitem}
```
![tabel4](https://user-images.githubusercontent.com/16071968/151435212-e062b318-6158-422f-8be8-add2b4eb83e1.PNG)


