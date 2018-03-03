---
title: "Utilisation de types de données TCHAR.H avec _MBCS | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- TCHAR.H data types
- MBCS data type
- _MBCS data type
ms.assetid: 48f471e7-9d2b-4a39-b841-16a0e15c0a18
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 05f2a5ae3ccf2ec8b9d9c1766bd5b02ed43dfbf7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="using-tcharh-data-types-with-mbcs"></a>Utilisation de types de données TCHAR.H avec _MBCS
**Section spécifique à Microsoft**  
  
 Comme indiqué dans la table de mappages de routines de texte générique (consultez [Mappages de texte générique](../c-runtime-library/generic-text-mappings.md)), lorsque la constante manifeste `_MBCS` est définie, une routine de texte générique donnée correspond à un des types suivants de routines :  
  
-   Une routine SBCS qui gère correctement les chaînes, caractères et caractères multioctets. Dans ce cas, les arguments de chaîne doivent être de type `char*`. Par exemple, `_tprintf` est mappé sur `printf` ; les arguments de chaîne dans `printf` sont de type `char*`. Si vous utilisez le type de données de texte générique `_TCHAR` pour vos types de chaîne, les types de paramètre formels et réels pour `printf` correspondent car `_TCHAR*` est mappé sur `char*`.  
  
-   Une routine spécifique à MBCS. Dans ce cas, les arguments de chaîne doivent être de type `unsigned char*`. Par exemple, `_tcsrev` est mappé sur `_mbsrev`, qui attend et retourne une chaîne de type `unsigned char*`. Là encore, si vous utilisez le type de données de texte générique `_TCHAR` pour vos types de chaîne, il y a un conflit de type potentiel, car `_TCHAR` correspond au type `char`.  
  
 Voici les trois solutions pour empêcher ce conflit de types (et les avertissements du compilateur C ou erreurs du compilateur C++ qui en découleraient) :  
  
-   Utiliser le comportement par défaut. TCHAR.H fournit des prototypes de routine de texte générique pour les routines dans les bibliothèques Runtime, comme dans l’exemple suivant.  
  
    ```  
    char *_tcsrev(char *);  
    ```  
  
     Dans le cas par défaut, le prototype pour `_tcsrev` est mappé sur `_mbsrev` via un thunk dans LIBC.LIB. Cela transforme les types des paramètres entrants `_mbsrev` et la valeur sortante de `_TCHAR *` (comme `char *`) en `unsigned char *`. Cette méthode garantit la correspondance de types lorsque vous utilisez `_TCHAR`, mais elle est relativement lente en raison de la surcharge d’appels de fonction.  
  
-   Utilisez la fonction inline en incorporant l’instruction du préprocesseur suivante dans votre code.  
  
    ```  
    #define _USE_INLINING  
    ```  
  
     Avec cette méthode, un thunk de fonction inline, fournit par TCHAR.H, mappe la routine de texte générique directement sur la routine MBCS appropriée. L’extrait de code suivant de TCHAR.H fournit un exemple de cette procédure.  
  
    ```  
    __inline char *_tcsrev(char *_s1)  
    {return (char *)_mbsrev((unsigned char *)_s1);}  
    ```  
  
     Si vous pouvez utiliser l’incorporation, il s’agit de la meilleure solution, car elle garantit une correspondance de types et ne présente aucun coût supplémentaire en termes de temps.  
  
-   Utilisez le mappage direct en incorporant l’instruction du préprocesseur suivante dans votre code.  
  
    ```  
    #define _MB_MAP_DIRECT  
    ```  
  
     Cette approche constitue une alternative rapide si vous ne souhaitez pas utiliser le comportement par défaut ou que vous ne pouvez pas utiliser l’incorporation. La routine de texte générique est alors mappée par une macro directement sur la version MBCS de la routine, comme dans l’exemple suivant de TCHAR.H.  
  
    ```  
    #define _tcschr _mbschr  
    ```  
  
 Lorsque vous adoptez cette approche, vous devez veiller à vous assurer que les types de données appropriés sont utilisés pour les arguments de chaîne et les valeurs de retour de chaîne. Vous pouvez utiliser la conversion de type pour assurer la bonne correspondance des types, ou vous pouvez utiliser le type de données de texte générique `_TXCHAR`. `_TXCHAR` correspond au type `char` dans le code SBCS, mais est mappé sur le type `unsigned char` dans le code MBCS. Pour plus d’informations sur les macros de texte générique, consultez [Mappages de texte générique](../c-runtime-library/generic-text-mappings.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Internationalisation](../c-runtime-library/internationalization.md)   
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)