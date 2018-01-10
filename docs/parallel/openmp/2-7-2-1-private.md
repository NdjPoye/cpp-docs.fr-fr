---
title: "2.7.2.1 privé | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a08faf39ab2f82d76a936c216ba6707bee5c240
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="2721-private"></a>2.7.2.1 private
Le `private` clause déclare les variables dans la liste variable être privée pour chaque thread dans une équipe. La syntaxe de la `private` clause est comme suit :  
  
```  
private(variable-list)  
```  
  
 Le comportement d’une variable spécifiée dans un `private` clause est comme suit. Nouvel objet dont la durée de stockage automatique est alloué pour la construction. La taille et l’alignement du nouvel objet sont déterminés par le type de la variable. Cette allocation se produit une fois pour chaque thread dans l’équipe, et un constructeur par défaut est appelé pour un objet de classe si nécessaire. dans le cas contraire, la valeur initiale est indéterminée.  L’objet d’origine est référencé par la variable a une valeur indéterminée lors de l’entrée à la construction, ne doit pas être modifiée dans l’étendue dynamique de la construction et a une valeur indéterminée la sortie de la construction.  
  
 Dans l’étendue lexicale de la construction de la directive, la variable fait référence le nouvel objet privé alloué par le thread.  
  
 Les restrictions à le `private` clause sont les suivantes :  
  
-   Une variable avec un type de classe qui est spécifié dans un `private` clause doit avoir un constructeur par défaut accessible et non équivoque.  
  
-   Une variable spécifiée dans un `private` clause ne doit pas avoir un **const**-type qualifié, sauf si elle a une classe de type avec un `mutable` membre.  
  
-   Une variable spécifiée dans un `private` clause ne doit pas avoir un type incomplet ou un type référence.  
  
-   Variables qui apparaissent dans le `reduction` clause d’une **parallèles** directive ne peut pas être spécifiée dans un `private` clause sur une directive de partage de travail qui est lié à la construction parallèle.