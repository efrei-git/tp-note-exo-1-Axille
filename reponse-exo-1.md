Achille LICHNEROWICZ 20231469 


--- QUESTION 1 ---
mkdir git-exo
cd git-exo
git init 

echo "1" > 1.txt  
git add 1.txt                  
git commit -m "Commit 0"               

echo "Modif1" >> 1.txt   
git commit -am "Commit 1"    
git checkout -b branch-1  
echo "Modif 2" >> 1.txt
git commit -am "Commit 2"
echo "Modif 3" >> 1.txt
git commit -am "Commit 3"

git checkout main  


echo "Modif 4" >> 1.txt
git commit -am "Commit 4"

echo "Modif 5" >> 1.txt
git commit -am "Commit 5"

git merge branch-1 -m "Commit 6 (Fusion de branch-1 dans main)"

git add 1.txt
git commit -m "Résolution conflit et fusion branch-1 dans main"



*   601913d (HEAD -> main) Résolution du conflit et fusion branch-1 dans main
|\
| * cafc6be (branch-1) Commit 3
| * 64b4d71 Commit 2
* | 15ecbf6 Commit 5
* | 6738b1d Commit 4
|/
* ce5359d Commit 1
* adc04ae Commit 0
___________________________________________________________________________________________________________________________________


--- QUESTION 2 ---
git checkout -b branch-2

git checkout main
echo "Modif7" >> 1.txt
git commit -am "Commit 7"

echo "Modif8" >> 1.txt
git commit -am "Commit 8"

git checkout branch-2
echo "Modif9" >> 1.txt
git commit -am "Commit 9"

echo "Modif10" >> 1.txt
git commit -am "Commit 10"

* 07bbe99 (HEAD -> branch-2) Commit 10
* a2c272c Commit 9
| * f7d9903 (main) Commit 8
| * c1c1a75 Commit 7
|/
*   601913d Résolution du conflit et fusion branch-1 dans main
|\
| * cafc6be (branch-1) Commit 3
| * 64b4d71 Commit 2
* | 15ecbf6 Commit 5
* | 6738b1d Commit 4
|/
* ce5359d Commit 1
* adc04ae Commit 0
___________________________________________________________________________________________________________________________________


--- QUESTION 3 ---
git checkout branch-2
git rebase main

git add 1.txt
git rebase --continue


* 8b81f78 (HEAD -> branch-2) Commit 10
* 36bcda3 Commit  9: Résolution de conflit dans 1.txt
* f7d9903 (main) Commit 8
* c1c1a75 Commit 7
*   601913d Résolution du conflit et fusion branch-1 dans main
|\
| * cafc6be (branch-1) Commit 3
| * 64b4d71 Commit 2
* | 15ecbf6 Commit 5
* | 6738b1d Commit 4
|/
* ce5359d Commit 1
* adc04ae Commit 0


--- QUESTION 4 ---
git checkout main
git merge branch-2

* 8b81f78 (HEAD -> main, branch-2) Commit 10
* 36bcda3 Commit  9: Résolution de conflit dans 1.txt
* f7d9903 Commit 8
* c1c1a75 Commit 7
*   601913d Résolution du conflit et fusion branch-1 dans main
|\
| * cafc6be (branch-1) Commit 3
| * 64b4d71 Commit 2
* | 15ecbf6 Commit 5
* | 6738b1d Commit 4
|/
* ce5359d Commit 1
* adc04ae Commit 0
