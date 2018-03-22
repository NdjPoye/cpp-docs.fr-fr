---
title: VCPROFILE_ALLOC_SCALE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VCPROFILE_ALLOC_SCALE
dev_langs:
- C++
helpviewer_keywords:
- VCPROFILE_ALLOC_SCALE environment variable
ms.assetid: 5cb5ce27-f9b8-489b-b46c-d6e9bcab2d34
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7b441f41106544633bd691c409fa04c989146f0
ms.sourcegitcommit: 5cd2e3e51ecc8d9fc0d889555b4bfa193ba1d6a5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/21/2018
---
# <a name="vcprofileallocscale"></a>VCPROFILE_ALLOC_SCALE
Modifier la quantité de mémoire allouée pour contenir les données de profil.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VCPROFILE_ALLOC_SCALE=scale_value  
```  
  
#### <a name="parameters"></a>Paramètres  
 `scale_value`  
 La valeur d’échelle pour la quantité de mémoire que vous souhaitez pour les scénarios de test en cours d’exécution.  La valeur par défaut est 1.  
  
## <a name="remarks"></a>Notes  
 Dans de rares cas, il ne sera pas y avoir assez de mémoire disponible pour prendre en charge lors de l’exécution de scénarios de test de collecte des données de profil.  Dans ce cas, vous pouvez augmenter la quantité de mémoire avec `VCPROFILE_ALLOC_SCALE`.  
  
 Si vous recevez un message d’erreur pendant une série de tests qui indique que vous disposez d’une mémoire insuffisante, affecter une valeur supérieure à `VCPROFILE_ALLOC_SCALE`, jusqu'à ce que l’exécution du test terminé sans erreurs de mémoire insuffisante.  
  
## <a name="example"></a>Exemple  
  
```  
set VCPROFILE_ALLOC_SCALE=2  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Variables d’environnement pour les optimisations guidées par profil](../../build/reference/environment-variables-for-profile-guided-optimizations.md)