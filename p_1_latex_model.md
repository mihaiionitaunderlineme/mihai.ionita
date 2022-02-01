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
Fara pachet avem ca rezultat<br>
![tabel1](/images/tabel1.PNG)
iar cu: <br>
```LaTeX
\usepackage{makecell} 
\setcellgapes{5pt}
```
<br>
![tabel2](/images/tabel2.PNG)<br>
Ca cerinta specifica aveam trecerea de la Nivelul I - Capitolul 4, Nivelul II - Subcapitolul 4,1 catre nivelul III care trebuia sa contina enumerarea pe baza de litere. 
Fara cod avem ca rezultat<br>
![tabel3](/images/tabel3.PNG)
iar cu: <br>
```LaTeX
\usepackage[shortlabels]{enumitem}
```
<br>
![tabel4](/images/tabel4.PNG) <br>
In vederea realizarii primei pagini s-a introdus secventa de cod <br>
```LaTeX
\newcommand{\size}[2]{{\fontsize{#1}{0}\selectfont#2}}
\newenvironment{sizepar}[2]
{\par\fontsize{#1}{#2}\selectfont}
{\par}
``` 
<br>
Iar pentru incadrarea in pagina secventa de cod <br>
```LaTeX
\RequirePackage[left=0.59in,right=0.59in,top=0.69in,bottom=1.39in]{geometry}
\setlength{\headsep}{0mm} 
 \addtolength{\textfloatsep}{-0.6cm}
  \addtolength{\abovecaptionskip}{-1.6cm}
```
<br>
facand astfel diferenta dintre (fara cod)<br>
![tabel5](/images/tabel5.PNG)
si dintre (cu cod)<br>
![tabel6](/images/tabel6.PNG)
<br>
Pentru ca aveam nevoie sa definesc numarul paginii ca nr. pagina din nr. total de pagini
comada realizata cu  <br>
```LaTeX
Pagina \thepage \hspace{1pt} din \pageref{LastPage} 
```
<br> am introdus pachetele: <br>
```LaTeX
\usepackage{lastpage} %numar pagina
\usepackage{fancyhdr} %numar pagina
```
<br>Comanda<br>
```LaTeX
\hspace{1pt} 
```
<br>face diferenta dintre (fara cod)<br>
![tabel7](/images/tabel7.PNG)
si dintre (cu cod)<br>
![tabel8](/images/tabel8.PNG)
<br>Pachetul mdframed<br>
```LaTeX
\usepackage{mdframed}
```
<br>alaturi de parametrii<br>
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
<br>permite setarea unor bare laterale de-a dreapta si de-a stanga textului. In documentele de calitate acest tip de marcare poate fi folosit pentru evidentierea modificarilor din document realizate fata de editia anterioara. 
In text pentru inceperea si incheierea marcajului lateral se introduc comenzile:<br>
```LaTeX
\begin{siderules}
\end{siderules}
```
