---
title: PogoSafeMode | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: PogoSafeMode
ms.assetid: 2daeeff7-44cb-417f-90eb-6b9edf658533
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1ce0f4fe011c730a3264cea65b7ab5d10dbcd7ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="pogosafemode"></a>PogoSafeMode
Spécifiez s’il faut utiliser le mode rapide ou en mode sans échec pour le profilage de l’application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
PogoSafeMode  
```  
  
## <a name="remarks"></a>Remarques  
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