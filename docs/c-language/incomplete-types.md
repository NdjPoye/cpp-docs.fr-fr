---
title: "Types incomplets | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "tableaux (C), types incomplets"
  - "types incomplets"
  - "structures, incomplet"
  - "types (C), incomplet"
  - "unions, incomplet"
  - "void (mot clé) (C)"
  - "void (mot clé) (C), incomplet"
ms.assetid: 01bc0cf6-9fa7-458c-9371-ecbe54ea6aee
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Types incomplets
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un type incomplet est un type qui décrit un identificateur, mais qui ne présente pas les informations nécessaires pour permettre d'en déterminer la taille.  Un « type incomplet » peut être :  
  
-   un type de structure dont vous n'avez pas encore spécifié les membres ;  
  
-   un type d'union dont vous n'avez pas encore spécifié les membres ;  
  
-   un type de tableau dont vous n'avez pas encore spécifié la dimension.  
  
 Le type void est un type incomplet qui ne peut pas être complété.  Pour compléter un type incomplet, spécifiez les informations manquantes.  Les exemples ci\-dessous montrent comment créer et compléter des types incomplets.  
  
-   Pour créer un type de structure incomplet, déclarez un type de structure sans spécifier ses membres.  Dans l'exemple ci\-dessous, le pointeur `ps` pointe vers un type de structure incomplet nommé `student`.  
  
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
  
-   Pour créer un type de tableau incomplet, déclarez un type de tableau sans spécifier son nombre de répétitions.  Par exemple :  
  
    ```  
    char a[];  /* a has incomplete type */  
    ```  
  
-   Pour compléter un type de tableau incomplet, déclarez le même nom ultérieurement dans la même portée en spécifiant son nombre de répétitions, comme suit :  
  
    ```  
    char a[25]; /* a now has complete type */  
    ```  
  
## Voir aussi  
 [Déclarations et types](../c-language/declarations-and-types.md)