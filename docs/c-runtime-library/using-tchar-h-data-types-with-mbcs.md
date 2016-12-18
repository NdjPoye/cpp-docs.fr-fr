---
title: "Utilisation de types de donn&#233;es TCHAR.H avec _MBCS | Microsoft Docs"
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
  - "_mbcs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_MBCS (type de données)"
  - "MBCS (type de données)"
  - "types de données TCHAR.H"
ms.assetid: 48f471e7-9d2b-4a39-b841-16a0e15c0a18
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Utilisation de types de donn&#233;es TCHAR.H avec _MBCS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Comme la table de mappages de routines de texte générique le montre \(voir l'[Generic\-Text Mappings](../c-runtime-library/generic-text-mappings.md)\), lorsqu'une constante manifeste `_MBCS` est définie, une routine de textes génériques déterminé map vers une des routines de ce genre:  
  
-   Une routine SBCS qui gère les octets, les caractères et les chaînes multioctets comme il convient.  Dans ce cas, les arguments de chaîne doivent être de type `char*`.  Par exemple, `_tprintf` correspond à `printf`; les arguments de chaîne de `printf` sont de types `char*`.  Si vous utilisez le type de données de texte générique `_TCHAR` pour vos types chaînes, les types de paramètres formels et actuels pour `printf` correspondent car `_TCHAR*` maps vers `char*`.  
  
-   Une routine spécifique à MBCS.  Dans ce cas, les arguments de chaîne doivent être de type `unsigned char*`.  Par exemple, `_tcsrev`  correspond à `_mbsrev`, qui attend et retourne une chaîne de type `unsigned char*`.  Encore une fois, si vous utilisez le type de données de texte générique  `_TCHAR`  pour vos types de chaînes, il peut se produire un conflit de type car `_TCHAR`  maps vers le type `char`.  
  
 Vous trouverez ci\-dessous trois solutions pour empêcher ce conflit de type \(et les avertissements du compilateur C ou les erreurs du compilateur C\+\+ qui peuvent en résulter\).  
  
-   Utilisez le comportement par défaut.  Tchar.h fournit des prototypes de routine de texte générique pour les routines dans les bibliothèques runtime, comme indiqué dans l'exemple suivant.  
  
    ```  
    char *_tcsrev(char *);  
    ```  
  
     Par défaut, le prototype pour `_tcsrev` mappe vers `_mbsrev` via une conversion de code dans LIBC.LIB.  Cette opération remplace les types des paramètres entrants `_mbsrev` et de valeur de retour `_TCHAR *` \(par exemple , `char *`\) vers `unsigned char *`.  Cette méthode permet la mise en correspondance des types lorsque vous utilisez `_TCHAR`, mais est lente en raison du temps de gestion nécessaire à l'appel de fonction.  
  
-   Utilisez la fonction inline en incorporant l'instruction du préprocesseur suivante dans votre code.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     Cette méthode effectue une conversion de code de fonction inline, par Tchar.h, permettant de mapper directement la routine du texte générique à la routine MBCS appropriée.  L'extrait de code suivant de Tchar.h fournit un exemple de cette méthode.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     La meilleure solution est d'utiliser une fonction inline, car elle garantit la mise en correspondance des types sans coût horaire supplémentaire.  
  
-   Utilisez le "direct mapping" en incorporant l'instruction du préprocesseur suivant dans votre code.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     Cette solution est appréciable si vous ne souhaitez pas utiliser le comportement par défaut ou ne pouvez pas utiliser la fonction inline.  Cette solution permet le mappage de la routine de texte générique par une macro directement en version MBCS de la routine, comme dans l'exemple suivant de Tchar.h.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
 Lorsque vous utilisez cette solution, vous devez vous assurer que des types de données appropriés sont utilisés pour les arguments de chaîne et les valeurs de chaîne de retour.  Vous pouvez utiliser le transtypage forcé pour assurer une correspondance de type correcte ou vous pouvez utiliser le type de données de texte générique `_TXCHAR` .  `_TXCHAR` correspond au type `char` dans le code SBCS mais correspond au type `unsigned char` dans le code MBCS.  Pour plus d'informations sur les macros de texte générique consultez [Generic\-Text Mappings](../c-runtime-library/generic-text-mappings.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Internationalisation](../c-runtime-library/internationalization.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)