 Hello World
1. Scopul lucrarii de laborator :  
De a se invata utilizarea unui Version Control System si modul de setare a unui server. 
 
2. Obiective  
Studierea Version Control Systems (git). 
Intelegerea si aplicarea comenzilor GIT. 3. Mersul lucrarii de laborator  
3.1 Cerintele : 
* Initializare unui nou repositoriu. 
* Configurarea VCS. 
* Crearea branch-urilor si commit pe ambele branch-uri 
* Resetarea branch-urilor la commit-urile anterioare  
* Merge la 2 branchuri. 
* Folosirea fisierului .gitignore.. 
* Rezolvarea conflictelor. 
 
3.2 Analiza lucrarii de laborator : 
Linkul repositoriului https://github.com/Tabuncicv/MIDPS.git 
 
Sunt mai multe modalitati de a initializa un repozitoriu pe github. Putem crea o mapa goala in care vom plasa gitul nostru prin intermediul comenzii git init. 
 
Urmatorul pas este crearea a noului repozitoriu pe care il vom crea utilizind urmatoarea comanda curl – u ‘USER’ https.//api.github.com/user/repos/ -d ‘{“name”:”NUME”}’. Unde cuvintele scrise cu CAPS se vor inlocui cu numele utilizatorului si numele repozitoruui. Dupa aceasta este necesar sa unim gitul nostru gol cu repozitoriul creat. Vom folosi urmatoare camonda git remote add origin “Linkul la repozitoriul nostru” 
 
                   Configurarea gitului consta in mai multe etape. La inceput vom configura numele si emailul prin intermediul urmatoarelor comenzi :
git config –global user.name “Numele” git config –global user.email “Email” 
 
                       Urmatorul pas consta in generarea  SSH key. Scriem ssh-keygen, iar cheia (publica) obtinuta o copiem in setarile noastre de pe github.com.                       Cum e  mentinut si in conditiile laboratorului, este de dorit sa initializam repozitorul nostru cu un fisier README.md si un .gitignore. In fisierul README.md vom adauga informatii pentru cei care se vor folosi de repozitoriu iar in fisierul .gitignore vom adauga toate fisierele ce trebuiesc ignorate (adica sa nu fie incarcate la moment ). 

 Vom adauga fisierele noi create pe repozitoriul nostru. Pentru aceasta vom avea nevoie de urmatoarele comenzi : git add * - comanda indexeaza toate fisierele. git commit –m “TEXT” – comanda face un snapshot la toate schimbarile noastre. git push origin master – comanda incarca toate fisierele indexate pe github.com 
 

Pentru a ne asigura ca am facut totul bine si nu avem probleme utilizam urmatoarele comenzi git: *git status *git show  
 
VCS ne permite sa avem mai multe branchuri. Din ENG branch semnifica “creanga”. Branchurile sunt utilizate cind lucram paralel la un proiect si apoi dorim sa combinam toate modificarile. 
 
git branch “name” – creeaza un branch nou cu numele “name”. git branch – vizualizarea branchurilor (* indica branchul curent). git branch –d “name” – sterge branchul “name”. git checkout –b “name” -  creeaza un branch nou cu numele “name” si face switch la el. 
 
 git checkout “name” – face switch la branchul “name”. git branch –u upstream/name – face track la branchul indicat din branchul curent. git branch –u upstream/name “name” – face track din branchul “name” la branchul indicat. git branch –track “name” upstream/name – creeaza branchul “name” si ii face track la branchul indicat.  git branch –unset-upstream – scoate trackingul la branchul in care ne aflam. 
 
Pot aparea conflicte in cazul cind dorim sa facem merge la 2 branch-uri si unele rinduri sunt diferite. In asa caz,pentru a elimina conflictele, folosim mergetool. Drept mergetool am ales kdiff3. Pentru kdiff3, in mod implicit folosim comanda : git config –global merge.tool kdiff3. 
 
 In continuare vom lucra cu 2 branchuri – “master” si “nou”. Vom crea in fiecare branch cite un fisier “tomerge” continutul caruia va fi diferit. 
 
In continuare facem merge si incercam sa rezolvam acest conflict  cu ajutorul kdiff3.  

