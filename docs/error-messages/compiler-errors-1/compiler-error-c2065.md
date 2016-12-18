---
title: "Erreur du compilateur C2065 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2065"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2065"
ms.assetid: 78093376-acb7-45f5-9323-5ed7e0aab1dc
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2065
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : identificateur non déclaré  
  
 Le type d'une variable doit être spécifié dans une déclaration avant de pouvoir être utilisé.  Les paramètres utilisés par une fonction doivent être spécifiés dans une déclaration ou un prototype pour que la fonction puisse être utilisée.  
  
 Causes possibles :  
  
1.  Le nom de l'identificateur est mal orthographié.  
  
2.  L'identificateur utilise une combinaison erronée de majuscules et minuscules.  
  
3.  Les guillemets de fermeture sont manquants après une constante de chaîne.  
  
4.  Vous compilez avec une version de débogage du runtime C, en déclarant une variable d'itérateur de bibliothèque standard C\+\+ dans une boucle `for`, puis en essayant d'utiliser cette variable d'itérateur en dehors de l'étendue de la boucle `for`.  La compilation d'un code de bibliothèque standard C\+\+ avec une version de débogage du runtime C implique [\/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md).  Consultez [Itérateurs de débogage, prise en charge](../../standard-library/debug-iterator-support.md) pour plus d'informations.  
  
5.  Vous appelez peut\-être une fonction dans un fichier d'en\-tête SDK qui n'est actuellement pas prise en charge dans votre environnement de génération.  
  
6.  Omission de fichiers Include nécessaires, en particulier si vous définissez `VC_EXTRALEAN`, `WIN32_LEAN_AND_MEAN` ou `WIN32_EXTRA_LEAN`.  Ces symboles excluent certains fichiers d'en\-tête de windows.h et afxv\_w32.h pour accélérer les compilations.  \(Recherchez dans windows.h et afxv\_w32.h une description à jour de ce qui est exclu.\)  
  
7.  Portée espace de noms incorrecte.  Par exemple, pour résoudre les fonctions et les opérateurs de la bibliothèque standard C\+\+ qui ne sont pas entièrement qualifiés, vous devez spécifier l'espace de noms `std` avec la directive `using`.  Dans l'exemple suivant, la compilation échoue car la directive `using` est commentée et que `cout` est défini dans l'espace de noms `std` :  
  
## Exemple  
 L'exemple suivant génère l'erreur C2065 et montre comment la corriger.  
  
```  
// C2065.cpp  
// compile with: /EHsc  
// using namespace std;   // Uncomment this line to fix  
#include <iostream>  
int main() {  
   cout << "Hello" << endl;   // C2065  
  
   // Or try the following line instead  
   std::cout << "Hello" << std::endl;  
}  
```  
  
## Exemple  
 Lorsque vous appelez une fonction générique, si l'argument de type prévu ne peut pas être déduit des paramètres utilisés, le compilateur signale une erreur.  Pour plus d'informations, consultez [Generic Functions \(C\+\+\/CLI\)](../../windows/generic-functions-cpp-cli.md).  
  
 L'exemple suivant génère l'erreur C2065 et montre comment la corriger.  
  
```  
// C2065_b.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
int main() {  
   // global generic function call  
   G<T>(10);   // C2065  
   G<int>(10);   // OK - fix with a specific type argument  
}  
```  
  
## Exemple  
 Cette erreur peut également être due à la mise en conformité du compilateur pour Visual C\+\+ 2005 : vérification des paramètres des attributs Visual C\+\+.  
  
 L'exemple suivant génère l'erreur C2065 et montre comment la corriger.  
  
```  
// C2065_c.cpp  
// compile with: /c  
[module(DLL, name=MyLibrary)];   // C2065  
// try the following line instead  
// [module(dll, name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```