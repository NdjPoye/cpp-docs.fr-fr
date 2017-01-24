---
title: "Prise en charge des contextes d&#39;activation dans l&#39;&#233;tat du module MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contextes d'activation (C++)"
  - "contextes d'activation (C++), prise en charge des MFC"
ms.assetid: 1e49eea9-3620-46dd-bc5f-d664749567c7
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge des contextes d&#39;activation dans l&#39;&#233;tat du module MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC crée un contexte d'activation en utilisant une ressource manifeste spécifiée par le module utilisateur.  Pour plus d'informations sur la façon dont les contextes d'activation sont créés, consultez les rubriques suivantes :  
  
-   [Activation Contexts](http://msdn.microsoft.com/library/aa374153)  
  
-   [Application Manifests](http://msdn.microsoft.com/library/aa374191)  
  
-   [Assembly Manifests](http://msdn.microsoft.com/library/aa374219)  
  
## Remarques  
 En lisant les rubriques [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)], notez que le mécanisme de contexte d'activation de MFC ressemble au contexte d'activation de [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] sauf que MFC n'utilise pas l'API de contexte d'activation de [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Le contexte d'activation s'exécute dans des applications MFC, des DLL d'utilisateur, et des DLL d'extension des manières suivantes :  
  
-   Les applications MFC utilisent l'ID de ressource 1 pour leur ressource manifeste.  Dans ce cas, le MFC ne crée pas son propre contexte d'activation, mais utilise le contexte d'application par défaut.  
  
-   Les DLL MFC utilisent l'ID de ressource 2 comme ressource de manifeste.  Ici, MFC crée un contexte d'activation pour chaque DLL utilisateur, de sorte que les DLL utilisateur peuvent utiliser des versions différentes des mêmes bibliothèques \(par exemple, la bibliothèque de contrôles communs\).  
  
-   Les DLL d'extension de MFC reposent sur leurs applications d'hébergement ou DLL utilisateur pour générer leur contexte d'activation.  
  
 Bien que l'état de contexte d'activation peut être modifié à l'aide de les processus décrits dans [Using the Activation Context API](http://msdn.microsoft.com/library/aa376620), l'utilisation du mécanisme de contexte d'activation de MFC peut être utile lors du développement des architectures de plug\-in basés sur des DLL de où il n'est pas simple \(ou impossible\) de basculer manuellement l'état d'activation avant et après les appels individuels aux connexions externes.  
  
 Le contexte d'activation est créé dans [AfxWinInit](../Topic/AfxWinInit.md).  Il est détruit dans le destructeur `AFX_MODULE_STATE`.  Un descripteur de contexte d'activation est conservé dans `AFX_MODULE_STATE`. \(`AFX_MODULE_STATE` est décrit dans [AfxGetStaticModuleState](../Topic/AfxGetStaticModuleState.md).\)  
  
 La macro [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md) active ou désactive le contexte d'activation.  `AFX_MANAGE_STATE` est activé pour les bibliothèques MFC statiques, ainsi que les DLL MFC, pour permettre au code de MFC de s'exécuter dans le contexte d'activation approprié sélectionné par la DLL utilisateur.  
  
## Voir aussi  
 [Activation Contexts](http://msdn.microsoft.com/library/aa374153)   
 [Application Manifests](http://msdn.microsoft.com/library/aa374191)   
 [Assembly Manifests](http://msdn.microsoft.com/library/aa374219)   
 [AfxWinInit](../Topic/AfxWinInit.md)   
 [AfxGetStaticModuleState](../Topic/AfxGetStaticModuleState.md)   
 [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md)