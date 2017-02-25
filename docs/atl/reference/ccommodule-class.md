---
title: "CComModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComModule class"
  - "DLL modules [C++], ATL"
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CComModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

As of ATL 7,0, `CComModule` est déconseillé : consultez [Classes de module ATL](../../atl/atl-module-classes.md) pour plus de détails.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
class CComModule : public _ATL_MODULE  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComModule::GetClassObject](../Topic/CComModule::GetClassObject.md)|Crée un objet de le CLSID spécifié.  Pour DLLs uniquement.|  
|[CComModule::GetModuleInstance](../Topic/CComModule::GetModuleInstance.md)|retourne `m_hInst` ;|  
|[CComModule::GetResourceInstance](../Topic/CComModule::GetResourceInstance.md)|retourne `m_hInstResource` ;|  
|[CComModule::GetTypeLibInstance](../Topic/CComModule::GetTypeLibInstance.md)|retourne `m_hInstTypeLib` ;|  
|[CComModule::Init](../Topic/CComModule::Init.md)|Initialise les données membres.|  
|[CComModule::RegisterClassHelper](../Topic/CComModule::RegisterClassHelper.md)|Écrit l'inscription standard de la classe d'un objet dans la base de registres.|  
|[CComModule::RegisterClassObjects](../Topic/CComModule::RegisterClassObjects.md)|Stocke l'objet de classe.  Pour EXE uniquement.|  
|[CComModule::RegisterServer](../Topic/CComModule::RegisterServer.md)|Met à jour la base de registres pour chaque objet dans la table d'objets.|  
|[CComModule::RegisterTypeLib](../Topic/CComModule::RegisterTypeLib.md)|Enregistre une bibliothèque de types.|  
|[CComModule::RevokeClassObjects](../Topic/CComModule::RevokeClassObjects.md)|Révoque l'objet de classe.  Pour EXE uniquement.|  
|[CComModule::Term](../Topic/CComModule::Term.md)|Récupère les données membres.|  
|[CComModule::UnregisterClassHelper](../Topic/CComModule::UnregisterClassHelper.md)|Supprime l'inscription standard de la classe d'un objet de la base de registres.|  
|[CComModule::UnregisterServer](../Topic/CComModule::UnregisterServer.md)|Annule l'inscription chaque objet dans la table d'objets.|  
|[CComModule::UpdateRegistryClass](../Topic/CComModule::UpdateRegistryClass.md)|Les registres ou annule l'inscription l'inscription standard de la classe d'un objet.|  
|[CComModule::UpdateRegistryFromResourceD](../Topic/CComModule::UpdateRegistryFromResourceD.md)|Exécute le script contenu dans une ressource spécifiée pour inscrire ou annuler l'inscription d'un objet.|  
|[CComModule::UpdateRegistryFromResourceS](../Topic/CComModule::UpdateRegistryFromResourceS.md)|Lie statiquement au composant de Registre ATL.  Exécute le script contenu dans une ressource spécifiée pour inscrire ou annuler l'inscription d'un objet.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComModule::m\_csObjMap](../Topic/CComModule::m_csObjMap.md)|Ensures a synchroniser l'accès aux informations de mappage d'objets.|  
|[CComModule::m\_csTypeInfoHolder](../Topic/CComModule::m_csTypeInfoHolder.md)|Ensures a synchroniser l'accès aux informations de bibliothèque de types.|  
|[CComModule::m\_csWindowCreate](../Topic/CComModule::m_csWindowCreate.md)|Ensures a synchroniser l'accès aux informations de classe de fenêtre et aux données statiques utilisées lors de la création de fenêtre.|  
|[CComModule::m\_hInst](../Topic/CComModule::m_hInst.md)|Contient le handle vers l'instance du module.|  
|[CComModule::m\_hInstResource](../Topic/CComModule::m_hInstResource.md)|Par défaut, contient le handle vers l'instance du module.|  
|[CComModule::m\_hInstTypeLib](../Topic/CComModule::m_hInstTypeLib.md)|Par défaut, contient le handle vers l'instance du module.|  
|[CComModule::m\_pObjMap](../Topic/CComModule::m_pObjMap.md)|Pointe vers la table d'objets mise à jour par l'instance du module.|  
  
## Notes  
  
> [!NOTE]
>  Cette classe est déconseillée, et les assistants de génération de code ATL utilisent maintenant [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) et les classes dérivées par [CAtlModule](../../atl/reference/catlmodule-class.md) .  Consultez [Classes de module ATL](../../atl/atl-module-classes.md) pour plus d'informations.  Les informations qui suivent utilisent avec les applications créées avec des versions plus anciennes ATL.  `CComModule` est toujours partie ATL pour en arrière la fonction.  
  
 `CComModule` implémente un module de serveur COM, ce qui permet à un client d'accéder aux composants du module.  `CComModule` prend en charge les modules de DLL \(in\-process\) et EXE \(local\).  
  
 Une instance d' `CComModule` utilise une table d'objets pour mettre à jour un ensemble de définitions d'objet de classe.  Cette table d'objets est implémentée comme tableau de structures d' `_ATL_OBJMAP_ENTRY` , et contient les informations pour :  
  
-   Écriture et supprimant des descriptions d'objet dans la base de registres.  
  
-   Instancier des objets via une fabrique de classe.  
  
-   Établir une communication entre un client et l'objet racine dans le composant.  
  
-   Effectuer la gestion de la durée de vie des objets de classe.  
  
 Lorsque vous exécutez l'ATL COM AppWizard, l'assistant génère automatiquement `_Module`, une instance globale d' `CComModule` ou une classe dérivée d'elle.  Pour plus d'informations sur l'Assistant Projet ATL, consultez l'article [Création d'un projet ATL](../../atl/reference/creating-an-atl-project.md).  
  
 En plus de `CComModule`, ATL fournit [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), qui implémente un module de modèle cloisonné pour EXE et services windows.  Dérivez votre package d' `CComAutoThreadModule` lorsque vous souhaitez créer des objets de plusieurs apartments.  
  
## Hiérarchie d'héritage  
 [\_ATL\_MODULE](../Topic/_ATL_MODULE.md)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## Configuration requise  
 `Header:` atlbase.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)