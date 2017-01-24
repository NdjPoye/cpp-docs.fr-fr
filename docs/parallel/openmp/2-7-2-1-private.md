---
title: "2.7.2.1 private | Microsoft Docs"
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
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.1 private
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la clause d' `private` déclare les variables dans la variable\-liste pour être privée à chaque thread dans une équipe.  La syntaxe de la clause d' `private` est la suivante :  
  
```  
private(variable-list)  
```  
  
 Le comportement d'une variable spécifiée dans une clause d' `private` est la suivante.  Un objet avec la durée automatique de stockage est alloué de l'élément.  la taille et l'alignement du nouvel objet sont déterminés par le type de la variable.  Cette allocation se produit une fois pour chaque thread dans l'équipe, et un constructeur par défaut est appelé pour un objet de classe si nécessaire ; sinon la valeur initiale est indéterminé.  L'objet d'origine référencé par la variable fait pas modifier une valeur indéterminée lors de l'entrée à l'élément, besoin dans l'étendue dynamique de l'élément, et a une valeur indéterminée lors de la sortie de l'élément.  
  
 Dans l'étendue lexicale de l'élément directive, la variable fait référence au nouvel objet privé alloué par le thread.  
  
 Les restrictions sur la clause d' `private` sont les suivantes :  
  
-   Une variable avec un type de classe qui est spécifié dans une clause d' `private` doit avoir un constructeur par défaut accessible et pas ambigu.  
  
-   une variable spécifiée dans une clause d' `private` ne doit pas avoir **const**\- type qualifié à moins qu'elle ait un type de classe avec un membre d' `mutable` .  
  
-   Une variable spécifiée dans une clause d' `private` ne doit pas avoir un type incomplet ou un type référence.  
  
-   Les variables qui apparaissent dans la clause d' `reduction` d'une directive de **parallèle** ne peuvent pas être spécifiées dans une clause d' `private` sur une directive de partage du travail qui se lie à l'élément parallèle.