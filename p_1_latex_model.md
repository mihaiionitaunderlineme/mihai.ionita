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
Fara pachet avem ca rezultat
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
In vederea realizarii primei pagini s-a introdus secventa de cod
```LaTeX
\newcommand{\size}[2]{{\fontsize{#1}{0}\selectfont#2}}
\newenvironment{sizepar}[2]
 {\par\fontsize{#1}{#2}\selectfont}
 {\par}
```
Iar pentru incadrarea in pagina secventa de cod
```LaTeX
\RequirePackage[left=0.59in,right=0.59in,top=0.69in,bottom=1.39in]{geometry}
\setlength{\headsep}{0mm} 
 \addtolength{\textfloatsep}{-0.6cm}
  \addtolength{\abovecaptionskip}{-1.6cm}
```
facand astfel diferenta dintre (fara cod)
![tabel5](https://user-images.githubusercontent.com/16071968/151440207-40880a03-5ea7-4c39-8c06-741ecbedaa15.PNG)
si dintre (cu cod)
![tabel6](https://user-images.githubusercontent.com/16071968/151440333-a1a7595b-f82d-4bb9-84d5-d61711e4f1c2.PNG)


Pentru ca aveam nevoie sa definesc numarul paginii ca nr. pagina din nr. total de pagini
comada realizata cu 
```LaTeX
Pagina \thepage \hspace{1pt} din \pageref{LastPage} 
```
am introdus pachetele:
```LaTeX
\usepackage{lastpage} %numar pagina
\usepackage{fancyhdr} %numar pagina
```
Comanda
```LaTeX
\hspace{1pt} 
```
face diferenta dintre (fara cod)
![tabel7](https://user-images.githubusercontent.com/16071968/151442504-378c32ce-a0bd-4d5d-a1e0-05a304149bb2.PNG)
si dintre (cu cod)
![tabel8](https://user-images.githubusercontent.com/16071968/151442515-ad2693c7-9497-4802-ac17-b1060c8ab445.PNG)
Pachetul mdframed
```LaTeX
\usepackage{mdframed}
```
alaturi de parametrii
```LaTeX
\newmdenv[
  topline=false,
  bottomline=false,
  skipabove=\topsep,
  skipbelow=\topsep,
  leftmargin=-10pt,
  rightmargin=-10pt,
  innertopmargin=0pt,
  innerbottommargin=0pt
]{siderules}
```
permite setarea unor bare laterale de-a dreapta si de-a stanga textului. In documentele de calitate acest tip de marcare poate fi folosit pentru evidentierea modificarilor din document realizate fata de editia anterioara. 
In text pentru inceperea si incheierea marcajului lateral se introduc comenzile:
```LaTeX
\begin{siderules}
\end{siderules}
```
