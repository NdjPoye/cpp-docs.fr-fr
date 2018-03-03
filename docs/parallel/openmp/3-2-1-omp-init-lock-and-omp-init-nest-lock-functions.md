---
title: 3.2.1 fonctions fonctions omp_init_lock and omp_init_nest_lock | Documents Microsoft
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
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3802822465d6527e4c98a0be6a8c274d767b0f52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 Fonctions omp_init_lock and omp_init_nest_lock
Ces fonctions vous permettent uniquement de l’initialisation d’un verrou. Chaque fonction initialise le verrou associé au paramètre *verrou* pour une utilisation dans les appels suivants. Le format est le suivant :  
  
```  
#include <omp.h>  
void omp_init_lock(omp_lock_t *lock);  
void omp_init_nest_lock(omp_nest_lock_t *lock);  
```  
  
 L’état initial est déverrouillé (autrement dit, aucun thread ne possède le verrou). Pour obtenir un verrou pouvant, le nombre initial d’imbrication est égale à zéro. Il n’est pas conforme à appeler une de ces routines avec une variable de verrou a déjà été initialisé.