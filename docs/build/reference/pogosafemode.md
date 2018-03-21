---
title: PogoSafeMode | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- PogoSafeMode
ms.assetid: 2daeeff7-44cb-417f-90eb-6b9edf658533
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5f40dad6feff9e49deeb495e8acbf2584dea3e41
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="pogosafemode"></a>PogoSafeMode
Spécifiez s’il faut utiliser le mode rapide ou en mode sans échec pour le profilage de l’application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
PogoSafeMode  
```  
  
## <a name="remarks"></a>Notes  
 L’optimisation guidée par profil (PGO) a deux modes possibles pendant la phase de profilage : mode rapide et mode sans échec. Lorsque le profilage est en mode rapide, il utilise le **INC** instruction pour incrémenter des compteurs de données. Le **INC** instruction est plus rapide, mais n’est pas thread-safe. Lorsque le profilage est en mode sans échec, il utilise le **LOCK INC** instruction pour incrémenter des compteurs de données. Le **LOCK INC** instruction a les mêmes fonctionnalités que le **INC** instruction a et qu’il est thread-safe, mais il est plus lente que la **INC** instruction.  
  
 Par défaut, le profilage PGO fonctionne en mode rapide. `PogoSafeMode`est uniquement requis si vous souhaitez utiliser le mode sans échec.  
  
 Pour exécuter le profilage PGO en mode sans échec, vous devez utiliser la variable d’environnement `PogoSafeMode` ou le commutateur de l’éditeur de liens **- PogoSafeMode**, selon le système. Si vous effectuez le profilage sur une x64 ordinateur, vous devez utiliser le commutateur de l’éditeur de liens. Si vous effectuez le profilage sur x86 ordinateur, vous devez définir la variable d’environnement à n’importe quelle valeur avant de commencer le processus d’optimisation.  
  
## <a name="example"></a>Exemple  
  
```  
set PogoSafeMode=1  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Variables d’environnement pour les optimisations guidées par profil](../../build/reference/environment-variables-for-profile-guided-optimizations.md)   
 [Optimisations guidées par profil](../../build/reference/profile-guided-optimizations.md)