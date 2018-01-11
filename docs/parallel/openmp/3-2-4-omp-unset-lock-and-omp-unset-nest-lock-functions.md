---
title: 3.2.4 fonctions fonctions omp_unset_lock and omp_unset_nest_lock | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dc71c6c31a1d93b6e9c9cce2cd4f7830502a1a2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="324-ompunsetlock-and-ompunsetnestlock-functions"></a>3.2.4 Fonctions omp_unset_lock and omp_unset_nest_lock
Ces fonctions vous permettent de libérer la possession d’un verrou. Le format est le suivant :  
  
```  
#include <omp.h>  
void omp_unset_lock(omp_lock_t *lock);  
void omp_unset_nest_lock(omp_nest_lock_t *lock);  
```  
  
 L’argument de chacune de ces fonctions doit pointer vers une variable initialisée verrou détenue par le thread d’exécution de la fonction. Le comportement est indéfini si le thread ne possède pas ce verrou.  
  
 Pour obtenir un verrou simple, le `omp_unset_lock` fonction libère le thread de l’exécution de la fonction à partir de la propriété du verrou.  
  
 Pour obtenir un verrou pouvant, le `omp_unset_nest_lock` fonction décrémente le nombre d’imbrication et libère le thread d’exécution de la fonction de la propriété du verrou si le nombre résultant est égal à zéro.