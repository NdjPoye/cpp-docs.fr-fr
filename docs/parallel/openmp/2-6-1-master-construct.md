---
title: "2.6.1 maître construction | Documents Microsoft"
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
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2517e19b49f1314e7432bb265756193ea3bb8f91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="261-master-construct"></a>2.6.1 Construction master
Le **master** directive identifie une construction qui spécifie un bloc structuré qui est exécuté par le thread principal de l’équipe. La syntaxe de la **master** la directive est la suivante :  
  
```  
#pragma omp master new-linestructured-block  
```  
  
 D’autres threads dans l’équipe n’exécutent pas le bloc structuré associé. Il n’existe aucune barrière implicite sur l’entrée ou sortie de la construction de référence.