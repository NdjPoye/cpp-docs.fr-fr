---
title: "__if_not_exists, instruction | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__if_not_exists"
  - "__if_not_exists_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__if_not_exists (mot clé) (C++)"
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __if_not_exists, instruction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'instruction `__if_not_exists` vérifie si l'identificateur spécifié existe.  S'il n'existe pas, le bloc d'instructions spécifié est exécuté.  
  
## Syntaxe  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`identifier`|Identificateur dont vous voulez tester l'existence.|  
|`statements`|Indique les instructions à exécuter si `identifier` n'existe pas.|  
  
## Notes  
  
> [!CAUTION]
>  Pour obtenir les résultats les plus fiables, utilisez l'instruction `__if_not_exists` sous les contraintes suivantes.  
  
-   Appliquez l'instruction `__if_not_exists` uniquement aux types simples, et non aux modèles.  
  
-   Appliquez l'instruction `__if_not_exists` aux identificateurs à l'intérieur ou à l'extérieur d'une classe.  N'appliquez pas l'instruction `__if_not_exists` aux variables locales.  
  
-   Utilisez l'instruction `__if_not_exists` uniquement dans le corps d'une fonction.  En dehors du corps d'une fonction, l'instruction `__if_not_exists` peut tester uniquement les types entièrement définis.  
  
-   Lorsque vous vérifiez la présence de fonctions surchargées, vous ne pouvez pas effectuer le test sur une forme spécifique de la surcharge.  
  
 Le complément de l'instruction `__if_not_exists` est l'instruction [\_\_if\_exists](../cpp/if-exists-statement.md).  
  
## Exemple  
 Pour obtenir un exemple illustrant l'utilisation de `__if_not_exists`, consultez [\_\_if\_exists, instruction](../cpp/if-exists-statement.md).  
  
## Voir aussi  
 [Instructions de sélection](../cpp/selection-statements-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [\_\_if\_exists, instruction](../cpp/if-exists-statement.md)