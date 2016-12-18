---
title: "CAtlServiceModuleT::Run Function | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule::Run"
  - "CServiceModule.Run"
  - "CSecurityDescriptor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL (services), sécurité"
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlServiceModuleT::Run Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Run** contient des appels à `PreMessageLoop`, à `RunMessageLoop`, et à `PostMessageLoop`.  Après avoir appelé, `PreMessageLoop` stocke d'abord l'ID du thread du service  Le service utilise cet ID pour se fermer en envoyant un message de **WM\_QUIT** à l'aide de la fonction de l'API Win32, [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946).  
  
 `PreMessageLoop` appelle ensuite `InitializeSecurity`.  Par défaut, `InitializeSecurity` appelle [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) avec le jeu de modèle de sécurité POUR ANNULER, ce qui signifie que tout utilisateur a accès à votre objet.  
  
 Si vous ne souhaitez pas que le service pour spécifier sa propre sécurité, la substitution `PreMessageLoop` et n'appellent pas `InitializeSecurity`, et COM détermine ensuite les paramètres de sécurité du Registre.  Un moyen pratique de configurer les paramètres du Registre consiste à utiliser l'utilitaire de [DCOMCNFG](../atl/dcomcnfg.md) décrite plus loin dans cette section.  
  
 Une fois la sécurité est spécifiée, l'objet est enregistré avec COM afin que les nouveaux clients puissent se connecter au programme.  Enfin, le programme indique le gestionnaire de contrôle des services \(SCM\) qu'il s'exécute et le programme écrit une boucle de message.  Le programme reste exécution jusqu'à ce qu'elle publie un message quitté à l'arrêt du service.  
  
## Voir aussi  
 [Services](../atl/atl-services.md)   
 [CSecurityDesc Class](../atl/reference/csecuritydesc-class.md)   
 [CSid Class](../atl/reference/csid-class.md)   
 [CDacl Class](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT::Run](../Topic/CAtlServiceModuleT::Run.md)