---
title: 2.7.2.7 copyin | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cd296192146e76085e1b987e29a377eb621917ae
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="2727-copyin"></a>2.7.2.7 copyin
Le **copyin** clause fournit un mécanisme pour attribuer la même valeur pour **threadprivate** variables pour chaque thread dans l’équipe de l’exécution de la région parallèle. Pour chaque variable spécifiée dans un **copyin** clause, la valeur de la variable dans le thread principal de l’équipe est copiée, comme lors d’affectation, pour les copies de thread privé au début de la région parallèle. La syntaxe de la **copyin** clause est comme suit :  
  
```  
  
copyin(  
variable-list  
)  
  
```  
  
 Les restrictions à le **copyin** clause sont les suivantes :  
  
-   Une variable qui est spécifiée dans le **copyin** clause doit avoir un opérateur d’assignation de copie accessible et non équivoque.  
  
-   Une variable qui est spécifiée dans le **copyin** clause doit être un **threadprivate** variable.