---
title: "2.7.2.4 partagé | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c9c5d653-58fc-4620-ab0a-443ac4f8ba2e
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 974f534003455ccd750ddc1b7c1f3c28b220f1b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="2724-shared"></a>2.7.2.4 shared
Cette clause partage les variables qui apparaissent dans le *variable-list* entre tous les threads dans une équipe. Accèdent à la même zone de stockage pour tous les threads dans une équipe **partagé** variables.  
  
 La syntaxe de la **partagé** clause est comme suit :  
  
```  
shared(variable-list)  
```