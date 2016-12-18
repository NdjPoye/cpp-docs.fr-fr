---
title: "2.7.2.3 lastprivate | Microsoft Docs"
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
ms.assetid: 77f6a5c9-704f-4a88-8476-29db852ed800
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.3 lastprivate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la clause d' `lastprivate` fournit un sur\-ensemble de la fonctionnalité fournie par la clause d' `private` .  La syntaxe de la clause d' `lastprivate` est la suivante :  
  
```  
lastprivate(variable-list)  
```  
  
 Les variables spécifiées dans *la variable\-liste* ont une sémantique de clause d' `private` .  Lorsqu'une clause d' `lastprivate` apparaît dans la directive qui identifie une construction de partage du travail, la valeur avec de chaque variable d' `lastprivate` de l'itération séquentiellement dernière de la boucle associée, la directive ou lexicale de dernière section, est affecté à l'objet d'origine de la variable.  Les variables qui ne sont pas assignées une valeur par la dernière itération de **pour** ou de **parallèle pour**, ou par la section lexicale dernière de la directive de **sections** ou de **sections parallèles** , ont des valeurs indéterminées après l'élément.  les sous\-objets non assignés ont également une valeur indéterminée après l'élément.  
  
 Les restrictions sur la clause d' `lastprivate` sont les suivantes :  
  
-   toutes les restrictions pour `private` s'appliquent.  
  
-   Une variable avec un type de classe qui est spécifié comme `lastprivate` doit avoir un opérateur d'assignation de copie accessible et pas ambigu.  
  
-   Les variables qui sont privées dans une région parallèle ou qui apparaissent dans la clause d' `reduction` d'une directive de **parallèle** ne peuvent pas être spécifiées dans une clause d' `lastprivate` sur une directive de partage du travail qui se lie à l'élément parallèle.