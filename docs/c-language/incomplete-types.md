---
title: Types incomplets | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C], incomplete
- types [C], incomplete
- incomplete types
- unions, incomplete
- arrays [C], incomplete types
- void keyword [C]
- structures, incomplete
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: ebc73813c28f5ccd25b28cadf283412a204b57d3
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="incomplete-types"></a>Types incomplets
Un type incomplet est un type qui décrit un identificateur, mais qui ne présente pas les informations nécessaires pour permettre d'en déterminer la taille. Un « type incomplet » peut être :  
  
-   un type de structure dont vous n'avez pas encore spécifié les membres ;  
  
-   un type d'union dont vous n'avez pas encore spécifié les membres ;  
  
-   un type de tableau dont vous n'avez pas encore spécifié la dimension.  
  
 Le type void est un type incomplet qui ne peut pas être complété. Pour compléter un type incomplet, spécifiez les informations manquantes. Les exemples ci-dessous montrent comment créer et compléter des types incomplets.  
  
-   Pour créer un type de structure incomplet, déclarez un type de structure sans spécifier ses membres. Dans l'exemple ci-dessous, le pointeur `ps` pointe vers un type de structure incomplet nommé `student`.  
  
    ```  
    struct student *ps;  
    ```  
  
-   Pour compléter un type de structure incomplet, déclarez le même type de structure ultérieurement dans la même portée en spécifiant ses membres, comme suit :  
  
    ```  
    struct student  
    {  
        int num;  
    }                   /* student structure now completed */  
    ```  
  
-   Pour créer un type de tableau incomplet, déclarez un type de tableau sans spécifier son nombre de répétitions. Exemple :  
  
    ```  
    char a[];  /* a has incomplete type */  
    ```  
  
-   Pour compléter un type de tableau incomplet, déclarez le même nom ultérieurement dans la même portée en spécifiant son nombre de répétitions, comme suit :  
  
    ```  
    char a[25]; /* a now has complete type */  
    ```  
  
## <a name="see-also"></a>Voir aussi  
 [Déclarations et types](../c-language/declarations-and-types.md)
