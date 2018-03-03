---
title: "Prise en charge des contextes d’Activation dans l’état du Module MFC | Documents Microsoft"
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
- activation contexts [MFC]
- activation contexts [MFC], MFC support
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41aa0987a6fad48e57544ebbdd708d60c000382e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="support-for-activation-contexts-in-the-mfc-module-state"></a>Prise en charge des contextes d'activation dans l'état du module MFC
MFC crée un contexte d’activation à l’aide d’une ressource de manifeste fournie par le module de l’utilisateur. Pour plus d’informations sur la création des contextes d’activation, consultez les rubriques suivantes :  
  
-   [Contextes d’activation](http://msdn.microsoft.com/library/aa374153)  
  
-   [Manifestes d’application](http://msdn.microsoft.com/library/aa374191)  
  
-   [Manifestes d’assembly](http://msdn.microsoft.com/library/aa374219)  
  
## <a name="remarks"></a>Notes  
 Lors de la lecture de ces rubriques du Kit de développement logiciel Windows, notez que le mécanisme de contexte d’activation MFC ressemble au contexte d’activation du SDK Windows mais MFC n’utilise pas l’API de contexte d’Activation Windows SDK.  
  
 Contexte d’activation fonctionne dans les applications MFC, les DLL de l’utilisateur et les DLL d’extension MFC, comme suit :  
  
-   Les applications MFC utilisent des ID de ressource 1 pour leurs ressources de manifeste. Dans ce cas, la bibliothèque MFC ne crée pas de son propre contexte d’activation, mais utilise le contexte d’application par défaut.  
  
-   Utilisateur MFC DLL utiliser les ID de ressource 2 pour leurs ressources de manifeste. Ici, MFC crée un contexte d’activation pour chaque DLL de l’utilisateur, afin de l’autre utilisateur DLL peut utiliser des versions différentes des mêmes bibliothèques (par exemple, la bibliothèque de contrôles communs).  
  
-   DLL d’extension MFC s’appuient sur leur hébergement applications ou un utilisateur DLL établir leur contexte d’activation.  
  
 Bien que l’état de contexte d’activation permettre être modifié à l’aide des processus décrits sous [à l’aide de l’API de contexte d’Activation](http://msdn.microsoft.com/library/aa376620), le mécanisme de contexte d’activation MFC peut s’avérer utile lors du développement des architectures de plug-in basées sur des DLL où il n’est pas facile (ou n’est pas possible) pour basculer manuellement l’état d’activation avant et après les appels aux plug-ins externes.  
  
 Le contexte d’activation est créé dans [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit). Il est détruit dans le `AFX_MODULE_STATE` destructeur. Un handle de contexte d’activation est conservé dans `AFX_MODULE_STATE`. (`AFX_MODULE_STATE` est décrit dans [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate).)  
  
 Le [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) macro active et désactive le contexte d’activation. `AFX_MANAGE_STATE`est activé pour les bibliothèques statiques MFC, ainsi que les DLL MFC, pour autoriser le code MFC à exécuter dans le contexte d’activation appropriée sélectionné par la DLL de l’utilisateur.  
  
## <a name="see-also"></a>Voir aussi  
 [Contextes d’activation](http://msdn.microsoft.com/library/aa374153)   
 [Manifestes d’application](http://msdn.microsoft.com/library/aa374191)   
 [Manifestes d’assembly](http://msdn.microsoft.com/library/aa374219)   
 [AfxWinInit](../mfc/reference/application-information-and-management.md#afxwininit)   
 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate)   
 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state)

