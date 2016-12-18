---
title: "Importation d&#39;appels de fonctions &#224; l&#39;aide de&#160;__declspec(dllimport) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__declspec"
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllimport) (mot clé C++)"
  - "dllimport (attribut) (C++), importations d'appel de fonction"
  - "appels de fonction (C++), importer"
  - "importer des appels de fonction (C++)"
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Importation d&#39;appels de fonctions &#224; l&#39;aide de&#160;__declspec(dllimport)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de code suivant montre comment utiliser **\_declspec\(dllimport\)** pour importer des appels de fonctions d'une DLL vers une application.  Supposons que `func1` est une fonction qui réside dans une DLL séparée du fichier .exe contenant la fonction **main**.  
  
 Sans **\_\_declspec\(dllimport\)** et étant donné ce code :  
  
```  
int main(void)   
{  
   func1();  
}  
```  
  
 le compilateur génère un code du genre :  
  
```  
call func1  
```  
  
 et l'éditeur de liens convertit l'appel en quelque chose qui ressemble à ceci :  
  
```  
call 0x4000000         ; The address of 'func1'.  
```  
  
 Si `func1` existe dans une autre DLL, l'éditeur de liens ne peut pas résoudre ce cas directement, car il n'a aucun moyen de déterminer l'adresse de `func1`.  Dans les environnements 16 bits, l'éditeur de liens ajoute cette adresse de code à une liste dans le fichier .exe que le chargeur pourrait corriger au moment de l'exécution avec l'adresse correcte.  Dans les environnements 32 bits et 64 bits, l'éditeur de liens génère un thunk dont il connaît l'adresse.  Dans un environnement 32 bits, le thunk se présente de la façon suivante :  
  
```  
0x40000000:    jmp DWORD PTR __imp_func1  
```  
  
 Ici `imp_func1` est l'adresse de l'emplacement de `func1` dans la table des adresses d'importation du fichier .exe.  Toutes les adresses sont ainsi connues de l'éditeur de liens.  Le chargeur doit seulement mettre à jour la table des adresses d'importation du fichier .exe au moment du chargement pour que tout fonctionne correctement.  
  
 Par conséquent, l'utilisation de **\_\_declspec\(dllimport\)** est plus indiquée car l'éditeur de liens ne génère un thunk que si c'est nécessaire.  Les thunks augmentent le volume du code \(sur les systèmes RISC, cela peut représenter plusieurs instructions\) et peuvent diminuer les performances du cache.  Si vous indiquez au compilateur que la fonction se trouve dans une DLL, il peut générer un appel indirect à votre place.  
  
 Ce code :  
  
```  
__declspec(dllimport) void func1(void);  
int main(void)   
{  
   func1();  
}  
```  
  
 génère ainsi l'instruction suivante :  
  
```  
call DWORD PTR __imp_func1  
```  
  
 Il n'existe ni thunk ni instruction `jmp`, de sorte que le code est plus petit et plus rapide.  
  
 D'un autre côté, vous ne souhaiterez probablement pas avoir à utiliser un appel indirect pour les appels de fonctions à l'intérieur d'une DLL.  Vous connaissez déjà l'adresse d'une fonction.  Comme il faut du temps et de l'espace pour charger et stocker l'adresse de la fonction avant un appel indirect, un appel direct est toujours plus rapide et plus court.  Vous souhaiterez utiliser **\_\_declspec\(dllimport\)** seulement pour appeler des fonctions de la DLL depuis l'extérieur de la DLL elle\-même.  N'utilisez pas **\_\_declspec\(dllimport\)** sur des fonctions à l'intérieur d'une DLL lors de la génération de cette DLL.  
  
## Voir aussi  
 [Importation dans une application](../build/importing-into-an-application.md)