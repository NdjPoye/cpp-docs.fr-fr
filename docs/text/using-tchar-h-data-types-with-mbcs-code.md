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
  - ""tchar.h""
  - "TCHAR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "types de données de texte générique (C++)"
  - "mappages de texte générique (C++)"
  - "mapper du texte générique"
  - "mappages (C++), TCHAR.H"
  - "MBCS (C++), mappages de texte générique"
  - "types de données TCHAR.H, mapper"
ms.assetid: 298583c5-22c3-40f6-920e-9ec96d42abd8
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Utilisation de types de donn&#233;es TCHAR.H avec _MBCS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque la constante de manifeste **\_MBCS** est définie, une routine de texte générique donnée correspond à l'un des types de routines suivants :  
  
-   Une routine SBCS qui gère les octets, les caractères et les chaînes multioctets comme il convient.  Dans ce cas, les arguments de chaîne doivent être de type **char\***.  Par exemple, `_tprintf` correspond à `printf`; les arguments de chaîne de `printf` sont de types **char\***.  Si vous utilisez le type de données de texte générique **\_TCHAR** pour vos types de chaînes, les types de paramètres formels et actuels pour `printf` correspondent car **\_TCHAR**\* correspond à **char\***.  
  
-   Une routine spécifique à MBCS.  Dans ce cas, les arguments de chaîne doivent être de type `unsigned` **char\***.  Par exemple, `_tcsrev` correspond à `_mbsrev`, qui attend et retourne une chaîne de type `unsigned` **char\***.  Si vous utilisez le type de données de texte générique **\_TCHAR** pour vos types de chaînes, il peut se produire un conflit de type car **\_TCHAR** correspond au type `char`.  
  
 Vous trouverez ci\-dessous trois solutions pour empêcher ce conflit de type \(et les avertissements du compilateur C ou les erreurs du compilateur C\+\+ qui peuvent en résulter\).  
  
-   Utilisez le comportement par défaut.  Tchar.h fournit des prototypes de routine de texte générique pour les routines dans les bibliothèques runtime, comme indiqué dans l'exemple suivant.  
  
    ```  
    char * _tcsrev(char *);  
    ```  
  
     Dans la casse par défaut, le prototype de `_tcsrev` mappe à `_mbsrev` via une conversion de code dans Libc.lib.  Cette opération remplace les types des paramètres entrants et de valeur de retour `_mbsrev` **\_TCHAR \*** \(autrement dit, `char` **\***\) par `unsigned` `char` **\***.  Cette méthode permet la mise en correspondance des types lorsque vous utilisez **\_TCHAR**, mais est lente en raison du temps de gestion nécessaire à l'appel de fonction.  
  
-   Utilisez la fonction inline en incorporant l'instruction du préprocesseur suivante dans votre code.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     Cette méthode provoque un thunk de fonction inline, par Tchar.h, permettant de mapper directement la routine de texte générique à la routine MBCS appropriée.  L'extrait de code suivant de Tchar.h fournit un exemple de cette méthode.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     La meilleure solution est d'utiliser une fonction inline, car elle garantit la mise en correspondance des types sans coût horaire supplémentaire.  
  
-   Utilisez le mappage direct en incorporant l'instruction du préprocesseur suivante dans votre code.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     Cette solution est appréciable si vous ne souhaitez pas utiliser le comportement par défaut ou ne pouvez pas utiliser la fonction inline.  Cette solution permet le mappage de la routine de texte générique par une macro directement en version MBCS de la routine, comme dans l'exemple suivant de Tchar.h.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
     Lorsque vous utilisez cette solution, vous devez utiliser les types de données appropriés pour les arguments de chaîne et les valeurs retournées de chaîne.  Vous pouvez utiliser la conversion de type forcée pour assurer une correspondance de type correcte ou vous pouvez utiliser le type de données de texte générique **\_TXCHAR**.  **\_TXCHAR** correspond au type `char` dans le code SBCS mais correspond au type `unsigned` `char` dans le code MBCS.  Pour plus d'informations sur les macros de texte générique, consultez [Mappages de texte générique](../c-runtime-library/generic-text-mappings.md) dans la *référence de la bibliothèque runtime*.  
  
## Voir aussi  
 [Mappages de texte générique dans Tchar.h](../text/generic-text-mappings-in-tchar-h.md)