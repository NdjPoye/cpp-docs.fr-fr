---
title: Fonction CAtlServiceModuleT::Run | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule::Run
- CServiceModule.Run
- CSecurityDescriptor
dev_langs:
- C++
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7ff3efe9298b7a2c11e7f83ef58640b2947519b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemoduletrun-function"></a>CAtlServiceModuleT::Run (fonction)
**Exécutez** contient des appels de `PreMessageLoop`, `RunMessageLoop`, et `PostMessageLoop`. Après avoir été appelé, `PreMessageLoop` stocke d’abord les ID de thread. du service Le service utilisera cet ID pour se fermer lui-même en envoyant un **WM_QUIT** de message à l’aide de la fonction API Win32, [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946).  
  
 `PreMessageLoop`appelle ensuite `InitializeSecurity`. Par défaut, `InitializeSecurity` appelle [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) avec le descripteur de sécurité la valeur NULL, ce qui signifie que n’importe quel utilisateur a accès à votre objet.  
  
 Si vous ne souhaitez pas que le service spécifie sa propre sécurité, substituez `PreMessageLoop` et n’appelez pas `InitializeSecurity`, et COM puis détermine les paramètres de sécurité à partir du Registre. Un moyen pratique de configurer les paramètres du Registre est la [DCOMCNFG](../atl/dcomcnfg.md) utilitaire décrit plus loin dans cette section.  
  
 Une fois que la sécurité est spécifiée, l’objet est enregistré avec COM afin que les nouveaux clients peuvent se connecter au programme. Enfin, le programme indique le Gestionnaire de contrôle des services (SCM) qu’il est en cours d’exécution et que le programme entre une boucle de message. Le programme continue de s’exécuter jusqu'à ce qu’il publie un message d’arrêt en cas d’arrêt du service.  
  
## <a name="see-also"></a>Voir aussi  
 [Services](../atl/atl-services.md)   
 [Classe de CSecurityDesc](../atl/reference/csecuritydesc-class.md)   
 [Classe de CSid](../atl/reference/csid-class.md)   
 [Classe de CDacl](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT::Run](../atl/reference/catlservicemodulet-class.md#run)

