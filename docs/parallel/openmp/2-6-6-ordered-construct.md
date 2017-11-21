---
title: 2.6.6 construction ordered | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 690db7cbc03e9aa9a3b4780dd2b115812c31f984
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="266-ordered-construct"></a>2.6.6 Construction ordered
Ce qui suit le bloc structuré une **classés** directive est exécutée dans l’ordre dans lequel les itérations sont exécutées dans une boucle séquentielle. La syntaxe de la **classés** la directive est la suivante :  
  
```  
#pragma omp ordered new-linestructured-block  
```  
  
 Un **classés** la directive doit être dans l’étendue dynamique d’un **pour** ou **parallèles pour** construire. Le **pour** ou **parallèles pour** directive auquel le **classés** construction lie doit avoir un **classés** clause est spécifiée comme décrit dans [Section 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) à la page 11. Dans l’exécution d’un **pour** ou **parallèles pour** construire avec un **classés** clause, **classés** constructions sont exécutées uniquement dans le ordre dans lequel elles sont exécutées dans une exécution séquentielle de la boucle.  
  
 Restrictions à le **classés** directive sont les suivantes :  
  
-   Une itération d’une boucle avec une **pour** construction ne doit pas exécuter plusieurs fois la même directive ordonnée et qu’il ne doit pas exécuter plusieurs **classés** directive.