---
title: "Erreur mathématique M6111 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- M6111
dev_langs:
- C++
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 204df0df4855fd2628a96ac326dd39c0d65151e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6111"></a>Erreur mathématique M6111
dépassement de capacité négatif de pile  
  
 Une opération à virgule flottante a provoqué un dépassement de capacité de pile sur le coprocesseur 8087/287/387 ou l’émulateur.  
  
 Cette erreur est souvent due à un appel à une `long double` fonction qui ne retourne pas de valeur. Par exemple, la commande suivante génère cette erreur lorsque compilé et exécuté :  
  
```  
long double ld() {};  
main ()  
{  
  ld();  
}  
```  
  
 Programme se termine par le code de sortie 139.