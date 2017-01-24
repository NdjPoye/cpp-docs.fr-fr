---
title: "CAtlServiceModuleT Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAtlServiceModuleT"
  - "ATL.CAtlServiceModuleT"
  - "CAtlServiceModuleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlServiceModuleT class"
ms.assetid: 8fc753ce-4a50-402b-9b4a-0a4ce5dd496c
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlServiceModuleT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente un service.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template <  
class T,  
UINT nServiceNameID   
>  
class ATL_NO_VTABLE CAtlServiceModuleT :  
public CAtlExeModuleT< T>  
```  
  
#### Paramètres  
 `T`  
 Votre classe dérivée d' `CAtlServiceModuleT`.  
  
 *nServiceNameID*  
 L'identificateur de ressource du service.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlServiceModuleT::CAtlServiceModuleT](../Topic/CAtlServiceModuleT::CAtlServiceModuleT.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlServiceModuleT::Handler](../Topic/CAtlServiceModuleT::Handler.md)|La routine de gestionnaire pour le service.|  
|[CAtlServiceModuleT::InitializeSecurity](../Topic/CAtlServiceModuleT::InitializeSecurity.md)|Fournit les paramètres de sécurité par défaut pour le service.|  
|[CAtlServiceModuleT::Install](../Topic/CAtlServiceModuleT::Install.md)|Installe et crée le service.|  
|[CAtlServiceModuleT::IsInstalled](../Topic/CAtlServiceModuleT::IsInstalled.md)|Confirme que le service a été installé.|  
|[CAtlServiceModuleT::LogEvent](../Topic/CAtlServiceModuleT::LogEvent.md)|Écrit dans le journal des événements.|  
|[CAtlServiceModuleT::OnContinue](../Topic/CAtlServiceModuleT::OnContinue.md)|Substituez cette méthode pour redémarrer le service.|  
|[CAtlServiceModuleT::OnInterrogate](../Topic/CAtlServiceModuleT::OnInterrogate.md)|Substituez cette méthode pour interroger le service.|  
|[CAtlServiceModuleT::OnPause](../Topic/CAtlServiceModuleT::OnPause.md)|Substituez cette méthode pour suspendre le service.|  
|[CAtlServiceModuleT::OnShutdown](../Topic/CAtlServiceModuleT::OnShutdown.md)|Substituez cette méthode pour arrêter le service|  
|[CAtlServiceModuleT::OnStop](../Topic/CAtlServiceModuleT::OnStop.md)|Substituez cette méthode pour arrêter le service|  
|[CAtlServiceModuleT::OnUnknownRequest](../Topic/CAtlServiceModuleT::OnUnknownRequest.md)|Substituez cette méthode pour traiter les requêtes inconnues au service|  
|[CAtlServiceModuleT::ParseCommandLine](../Topic/CAtlServiceModuleT::ParseCommandLine.md)|Analyse la ligne de commande et exécute l'inscription si nécessaire.|  
|[CAtlServiceModuleT::PreMessageLoop](../Topic/CAtlServiceModuleT::PreMessageLoop.md)|Cette méthode est appelée juste avant écrire la boucle de message.|  
|[CAtlServiceModuleT::RegisterAppId](../Topic/CAtlServiceModuleT::RegisterAppId.md)|Stocke le service dans le Registre.|  
|[CAtlServiceModuleT::Run](../Topic/CAtlServiceModuleT::Run.md)|Dirige le service.|  
|[CAtlServiceModuleT::ServiceMain](../Topic/CAtlServiceModuleT::ServiceMain.md)|La méthode appelée par le gestionnaire de contrôle des services.|  
|[CAtlServiceModuleT::SetServiceStatus](../Topic/CAtlServiceModuleT::SetServiceStatus.md)|Met à jour l'état du service.|  
|[CAtlServiceModuleT::Start](../Topic/CAtlServiceModuleT::Start.md)|Appelé par `CAtlServiceModuleT::WinMain` lorsque le service démarre.|  
|[CAtlServiceModuleT::Uninstall](../Topic/CAtlServiceModuleT::Uninstall.md)|Les points et supprime le service.|  
|[CAtlServiceModuleT::Unlock](../Topic/CAtlServiceModuleT::Unlock.md)|Décrémente le nombre de verrous du service.|  
|[CAtlServiceModuleT::UnregisterAppId](../Topic/CAtlServiceModuleT::UnregisterAppId.md)|Supprime le service du Registre.|  
|[CAtlServiceModuleT::WinMain](../Topic/CAtlServiceModuleT::WinMain.md)|Cette méthode implémente le code requis pour exécuter le service.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CAtlServiceModuleT::m\_bService](../Topic/CAtlServiceModuleT::m_bService.md)|La balise indiquant le programme s'exécute en tant que service.|  
|[CAtlServiceModuleT::m\_dwThreadID](../Topic/CAtlServiceModuleT::m_dwThreadID.md)|Variable membre enregistrant l'identificateur de thread.|  
|[CAtlServiceModuleT::m\_hServiceStatus](../Topic/CAtlServiceModuleT::m_hServiceStatus.md)|Variable membre enregistrement d'un handle vers la structure d'informations d'état pour le service actuel.|  
|[CAtlServiceModuleT::m\_status](../Topic/CAtlServiceModuleT::m_status.md)|Variable membre stockant la structure d'informations d'état pour le service actuel.|  
|[CAtlServiceModuleT::m\_szServiceName](../Topic/CAtlServiceModuleT::m_szServiceName.md)|Le nom du service est enregistré.|  
  
## Notes  
 `CAtlServiceModuleT`, dérivé de [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md), implémente un module de service ATL.  `CAtlServiceModuleT` fournit des méthodes pour traiter, l'installation, l'enregistrement, et suppression de ligne de commande.  Si la fonctionnalité supplémentaire est requise, ceux\-ci et d'autres méthodes peuvent être substitués.  
  
 Cette classe substitue [classe de CComModule](../../atl/reference/ccommodule-class.md) obsolète utilisé dans les versions antérieures ATL.  Consultez [Classes de module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
## Hiérarchie d'héritage  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlExeModuleT](../../atl/reference/catlexemodulet-class.md)  
  
 `CAtlServiceModuleT`  
  
## Configuration requise  
 **Header:** atlbase.h  
  
## Voir aussi  
 [CAtlExeModuleT Class](../../atl/reference/catlexemodulet-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)