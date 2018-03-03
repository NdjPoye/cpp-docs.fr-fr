---
title: 2.7.2.7 copyin | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5ba09b70b3a3591b1f8b427ac107576cfcac7935
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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