---
title: "Le chargement de toutes les importations pour une DLL à chargement différé | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 842b23afe7aec4d66eaf0787976d8e0c5d9a7320
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>Chargement de toutes les importations pour une DLL à chargement différé
Le **__HrLoadAllImportsForDll** fonction, définie dans delayhlp.cpp, indique à l’éditeur de liens de charger toutes les importations d’une DLL qui a été spécifiée avec la [DELAYLOAD](../../build/reference/delayload-delay-load-import.md) option de l’éditeur de liens.  
  
 Le chargement de toutes les importations vous permet de placer dans un seul emplacement dans votre code de gestion des erreurs et n’a pas à utiliser autour des appels réels pour les importations de gestion des exceptions. Il permet également d’éviter une situation où votre application échoue partiellement via un processus à la suite le code d’assistance ne parvient pas à charger une importation.  
  
 Appel de **__HrLoadAllImportsForDll** ne modifie pas le comportement des raccordements et erreur gestion ; consultez [gestion des erreurs et Notification](../../build/reference/error-handling-and-notification.md) pour plus d’informations.  
  
 Le nom de la DLL passé à **__HrLoadAllImportsForDll** est comparé à celui stocké à l’intérieur de la DLL elle-même et respecte la casse.  
  
 L’exemple suivant montre comment appeler **__HrLoadAllImportsForDll**:  
  
```  
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {  
   printf ( "failed on snap load, exiting\n" );  
   exit(2);  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de l’éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)