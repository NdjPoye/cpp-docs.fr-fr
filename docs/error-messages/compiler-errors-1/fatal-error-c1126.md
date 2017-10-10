---
title: "Erreur irrécupérable C1126 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1126
dev_langs:
- C++
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4f5346a3adb5535242207ebc3a3c9b2fcffa7a40
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1126"></a>Erreur irrécupérable C1126
'identificateur' : l’allocation automatique dépasse la taille  
  
 Espace alloué pour les variables locales d’une fonction (plus une quantité limitée de l’espace utilisé par le compilateur, notamment un supplémentaire de 20 octets pour les fonctions échangeables) dépasse la limite.  
  
 Pour corriger cette erreur, utilisez `malloc` ou `new` pour allouer de grandes quantités de données.
