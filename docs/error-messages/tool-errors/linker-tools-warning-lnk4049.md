---
title: "Avertissement des outils &#201;diteur de liens LNK4049 | Microsoft Docs"
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
  - "LNK4049"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4049"
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

symbole 'symbol' défini localement importé  
  
 Le symbole a été à la fois exporté depuis et importé vers le programme.  
  
 Cet avertissement est généré par l'éditeur de liens lorsque vous déclarez un symbole en utilisant l'attribut de classe de stockage `__declspec(dllexport)` dans un fichier objet et le référencez en utilisant l'attribut `__declspec(dllimport)` dans un autre.  
  
 L'avertissement LNK4049 est une version plus générale de [Avertissement des outils Éditeur de liens LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md).  L'éditeur de liens génère l'avertissement LNK4049 lorsqu'il ne peut pas déterminer de quelle fonction le symbole importé a été référencé.  
  
 Les cas courants où LNK4049 est généré à la place de LNK4217 sont :  
  
-   Exécution d'une liaison incrémentielle à l'aide de l'option [\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md).  
  
-   Exécution de l'optimisation de la totalité du programme à l'aide de l'option [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  
  
 Pour résoudre l'erreur LNK4049, effectuez l'une des opérations suivantes :  
  
-   Supprimez la déclaration de nom `__declspec(dllimport)` de la déclaration anticipée du symbole qui a déclenché LNK4049.  Vous pouvez rechercher les symboles au sein d'une image binaire à l'aide de l'utilitaire **DUMPBIN**.  Le commutateur **DUMPBIN \/SYMBOLS** affiche la table de symboles COFF de l'image.  Pour plus d'informations sur l'utilitaire **DUMPBIN**, consultez [Référence DUMPBIN](../../build/reference/dumpbin-reference.md).  
  
-   Désactivez temporairement la liaison incrémentielle et l'optimisation de la totalité du programme.  La recompilation de l'application génère l'avertissement LNK4217, lequel inclut le nom de la fonction à partir de laquelle le symbole importé a été référencé.  Supprimez la déclaration `__declspec(dllimport)` du symbole importé et activez la liaison incrémentielle ou l'optimisation de la totalité du programme comme requis.  
  
 Même si le code final généré se comporte correctement, le code généré pour appeler la fonction importée est moins efficace que l'appel direct de la fonction.  Cet avertissement n'apparaît pas lorsque vous compilez en utilisant l'option [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Pour plus d'informations sur les déclarations des données d'importation et d'exportation, consultez [dllexport, dllimport](../../cpp/dllexport-dllimport.md).  
  
## Exemple  
 La liaison des deux modules suivants génère LNK4049.  Le premier module génère un fichier objet qui contient une seule fonction exportée.  
  
```  
// LNK4049a.cpp  
// compile with: /c  
  
__declspec(dllexport) int func()   
{  
   return 3;  
}  
```  
  
## Exemple  
 Le deuxième module génère un fichier objet qui contient une déclaration anticipée de la fonction exportée dans le premier module, ainsi qu'un appel de cette fonction à l'intérieur de la fonction `main`.  La liaison de ce module avec le premier module génère LNK4049.  La suppression de la déclaration `__declspec(dllimport)` résout l'avertissement.  
  
```  
// LNK4049b.cpp  
// compile with: /link /WX /LTCG LNK4049a.obj  
// LNK4049 expected  
  
__declspec(dllimport) int func();  
// try the following line instead  
// int func();  
  
int main()  
{  
   return func();  
}  
```  
  
## Voir aussi  
 [Avertissement des outils Éditeur de liens LNK4217](../../error-messages/tool-errors/linker-tools-warning-lnk4217.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)