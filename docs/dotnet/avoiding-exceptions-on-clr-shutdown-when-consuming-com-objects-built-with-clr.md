---
title: "Éviter les Exceptions levées par les objets COM générés avec - clr | Documents Microsoft"
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
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 287c9831f8c604272b37ac85528d66fe640de557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>Éviter des exceptions à l'arrêt du CLR lors de l'utilisation d'objets COM générés avec /clr
Une fois que le common language runtime (CLR) entre en mode arrêt, les fonctions natives ont un accès limité aux services CLR. Lorsque vous tentez d’appeler Release sur un objet COM compilé avec **/CLR**, le CLR passe en code natif, puis revient en code managé pour répondre à l’appel IUnknown::Release (qui est définie dans le code managé). Le CLR empêche l’appel en code managé, car il est en mode arrêt.  
  
 Pour résoudre ce problème, assurez-vous que destructeurs appelés à partir des méthodes de mise en production ne doivent contenir du code natif.  
  
## <a name="see-also"></a>Voir aussi  
 [Assemblys mixtes (natif et managé)](../dotnet/mixed-native-and-managed-assemblies.md)