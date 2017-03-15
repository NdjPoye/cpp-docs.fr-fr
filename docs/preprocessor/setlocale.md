---
title: "setlocale | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "setlocale_CPP"
  - "vc-pragma.setlocale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pragmas, setlocale"
  - "setlocale (pragma)"
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# setlocale
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les paramètres régionaux \(pays\/région et langue\) à utiliser lors de la conversion des constantes à caractères larges et des littéraux de chaîne.  
  
## Syntaxe  
  
```  
  
#pragma setlocale( "[locale-string]" )  
```  
  
## Notes  
 Étant donné que l'algorithme de conversion des caractères multioctets en caractères larges peut varier selon les paramètres régionaux ou que la compilation peut avoir lieu sous des paramètres régionaux différents de ceux sous lesquels un fichier exécutable sera exécuté, ce pragma permet de spécifier les paramètres régionaux cibles au moment de la compilation.  Cela garantit que les chaînes à caractères larges seront stockées au format correct.  
  
 L'élément *locale\-string* par défaut est "".  
  
 Les paramètres régionaux « C » mappent chaque caractère de la chaîne à sa valeur comme `wchar_t` \(court non signé\).  Les autres valeurs valides pour `setlocale` sont les entrées qui se trouvent dans la liste des [Chaînes de langage](../c-runtime-library/language-strings.md).  Par exemple, vous pouvez émettre la commande suivante :  
  
```  
#pragma setlocale("dutch")  
```  
  
 La capacité à publier une chaîne de langue dépend de la prise en charge des pages de codes et des ID de langue sur votre ordinateur.  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)