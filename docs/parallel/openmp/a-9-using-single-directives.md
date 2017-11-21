---
title: "Directives uniques à l’aide A.9 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 101d6570f2e3c3e757f28ffb632633d6570dac06
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="a9---using-single-directives"></a>A.9   Utilisation de directives simples
L’exemple suivant illustre la `single` directive ([Section 2.4.3](../../parallel/openmp/2-4-3-single-construct.md) page 15). Dans l’exemple, un seul thread (généralement le premier thread qui rencontre le `single` directive) imprime le message de progression. L’utilisateur ne doit pas faire d’hypothèses comme pour le thread s’exécute le `single` section. Tous les autres threads ignorera la `single` section et s’arrêter à la barrière à la fin de la `single` construire. Si les autres threads peuvent continuer sans attendre que le thread qui exécute le `single` section, un `nowait` clause peut être spécifiée sur le `single` la directive.  
  
```  
#pragma omp parallel  
{  
    #pragma omp single  
        printf_s("Beginning work1.\n");  
    work1();  
    #pragma omp single  
        printf_s("Finishing work1.\n");  
    #pragma omp single nowait  
        printf_s("Finished work1 and beginning work2.\n");  
    work2();  
}  
```