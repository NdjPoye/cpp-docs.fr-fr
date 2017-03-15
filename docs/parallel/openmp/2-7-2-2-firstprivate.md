---
title: "2.7.2.2 firstprivate | Microsoft Docs"
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
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.2 firstprivate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la clause de **firstprivate** fournit un sur\-ensemble de la fonctionnalité fournie par la clause de **privé** .  La syntaxe de la clause de **firstprivate** est la suivante :  
  
```  
firstprivate(variable-list)  
```  
  
 Les variables spécifiées dans *la variable\-liste* ont une sémantique de clause de **privé** , comme décrit dans [section 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) à la page 25.  L'initialisation ou la construction se produit comme si elle était faites une fois par thread, avant l'exécution du thread de l'élément.  Pour une clause de **firstprivate** sur un élément parallèle, la valeur initiale du nouvel objet privé est la valeur de l'objet d'origine qui existe immédiatement avant l'élément parallèle pour le thread qui s'il rencontre.  Pour une clause de **firstprivate** sur un élément de partage du travail, la valeur initiale du nouvel objet privé pour chaque thread qui exécute l'élément de partage de travail est la valeur de l'objet d'origine qui existe avant le moment où le même thread rencontrera l'élément de partage du travail.  De plus, pour les objets C\+\+, le nouvel objet privé pour chaque thread est construite copie de l'objet d'origine.  
  
 Les restrictions sur la clause de **firstprivate** sont les suivantes :  
  
-   Une variable spécifiée dans une clause de **firstprivate** ne doit pas avoir un type incomplet ou un type référence.  
  
-   Une variable avec un type de classe qui est spécifié comme **firstprivate** doit avoir un constructeur de copie accessible et pas ambigu.  
  
-   Les variables qui sont privées dans une région parallèle ou qui apparaissent dans la clause de **réduction** d'une directive de **parallèle** ne peuvent pas être spécifiées dans une clause de **firstprivate** sur une directive de partage du travail qui se lie à l'élément parallèle.