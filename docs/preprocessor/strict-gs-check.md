---
title: "strict_gs_check | Microsoft Docs"
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
  - "strict_gs_check"
  - "strict_gs_check_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strict_gs_check (pragma)"
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strict_gs_check
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce pragma fournit une vérification de la sécurité renforcée.  
  
## Syntaxe  
  
```  
#pragma strict_gs_check([push,] on )   
#pragma strict_gs_check([push,] off )   
#pragma strict_gs_check(pop)  
```  
  
## Notes  
 Indique au compilateur qu'il faut insérer un cookie aléatoire dans la pile de fonction pour faciliter la détection de certaines catégories de dépassement de mémoire tampon basé sur la pile.  Par défaut, l'option du compilateur \/GS \(vérification de sécurité de la mémoire tampon\) n'insère pas un cookie pour toutes les fonctions.  Pour plus d'informations, consultez [\/GS \(vérification de la sécurité des mémoires tampons\)](../build/reference/gs-buffer-security-check.md).  
  
 Vous devez compiler avec \/GS \(vérification de sécurité de la mémoire tampon\) pour activer strict\_gs\_check.  
  
 Utilisez ce pragma dans les modules de code qui sont exposés à des données potentiellement nuisibles.  Ce pragma est très agressif. Il est appliqué à des fonctions qui peuvent ne pas avoir besoin de cette défense, mais il est optimisé pour minimiser son effet sur les performances de l'application résultante.  
  
 Même si vous utilisez ce pragma, vous devez vous efforcer d'écrire du code sécurisé.  Autrement dit, assurez\-vous que votre code n'a aucun dépassement de mémoire tampon. strict\_gs\_check peut protéger votre application contre les dépassements de mémoire tampon qui restent dans votre code.  
  
## Exemple  
 Dans le code suivant, un dépassement de mémoire tampon se produit lorsque nous copions un tableau dans un tableau local.  Lorsque vous compilez ce code avec \/GS, aucun cookie n'est inséré dans la pile, car le type de données tableau est un pointeur.  L'ajout du pragma strict\_gs\_check force l'insertion du cookie de pile dans la pile de fonction.  
  
```cpp  
// pragma_strict_gs_check.cpp  
// compile with: /c  
  
#pragma strict_gs_check(on)  
  
void ** ReverseArray(void **pData,  
                     size_t cData)  
{  
    // *** This buffer is subject to being overrun!! ***  
    void *pReversed[20];  
  
    // Reverse the array into a temporary buffer  
    for (size_t j = 0, i = cData; i ; --i, ++j)  
        // *** Possible buffer overrun!! ***  
            pReversed[j] = pData[i];   
  
    // Copy temporary buffer back into input/output buffer  
    for (size_t i = 0; i < cData ; ++i)   
        pData[i] = pReversed[i];  
  
    return pData;  
}  
  
```  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [\/GS \(vérification de la sécurité des mémoires tampons\)](../build/reference/gs-buffer-security-check.md)