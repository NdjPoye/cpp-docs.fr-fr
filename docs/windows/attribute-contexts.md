---
title: "Attribute Contexts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], contexts"
ms.assetid: 3086351f-77a8-4048-99e9-3b6b041b9437
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Attribute Contexts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les attributs C\+\+ peuvent être décrits à quatre champs de base : la cible ils peuvent être appliqués \(**s'applique à**\), si elles sont reproductibles ou non \(**reproductible**\), la présence requise des autres attributs \(**attributs requis**\), et les incompatibilités avec d'autres attributs \(**attributs valides**\).  Ces champs sont répertoriés dans un tableau sans dans la rubrique de référence de chaque attribut.  Chacun de ces champs est décrite ci\-dessous.  
  
## S'applique à  
 Ce champ décrit les différents éléments de langage C\+\+ qui sont des cibles valides de l'attribut spécifié.  Par exemple, si un attribut spécifie la « classe » dans le domaine de **s'applique à** , cela indique que l'attribut peut être appliqué qu'à une classe conforme C\+\+.  Si l'attribut est appliqué à une fonction membre d'une classe, une erreur de syntaxe résultant.  
  
 Pour plus d'informations, consultez l' [attributs par utilisation](../windows/attributes-by-usage.md).  
  
## reproductible  
 Ce champ indique si l'attribut peut être à plusieurs reprises appliqué à la même cible.  la majorité d'attributs ne sont pas reproductible.  
  
## attributs requis  
 Ce listes de champs d'autres attributs qui doivent être présents \(autrement dit, appliqué à la même cible\) pour que l'attribut spécifié fonctionne correctement.  Il est rare qu'un attribut possède toutes les entrées pour ce champ.  
  
## attributs valides  
 ce listes de champs d'autres attributs qui sont incompatibles avec l'attribut spécifié.  Il est rare qu'un attribut possède toutes les entrées pour ce champ.  
  
## Voir aussi  
 [C\+\+ Attributes Reference](../windows/cpp-attributes-reference.md)