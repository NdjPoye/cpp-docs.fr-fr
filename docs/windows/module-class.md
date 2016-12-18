---
title: "Module, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Module (classe)"
ms.assetid: dd67e3b8-c2e1-4f53-8c0f-565a140ba649
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Module, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente une collection d'objets connexes.  
  
## Syntaxe  
  
```  
  
template<  
   ModuleType moduleType  
>  
class Module;  
  
template<>  
class Module<InProc> : public Details::ModuleBase;  
  
template<>  
class Module<OutOfProc> : public Module<InProc>;  
```  
  
#### Paramètres  
 `moduleType`  
 Une combinaison d'une ou plusieurs valeurs d'énumération [ModuleType](../windows/moduletype-enumeration.md).  
  
## Membres  
  
### Classes protégées  
  
|Name|Description|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier, classe](../windows/module-genericreleasenotifier-class.md)|Appelle un gestionnaire d'événements lorsque le dernier objet du module actuel est libéré.  Le gestionnaire d'événements est spécifié sur un lambda, un functor, ou un pointeur fonction.|  
|[Module::MethodReleaseNotifier, classe](../windows/module-methodreleasenotifier-class.md)|Appelle un gestionnaire d'événements lorsque le dernier objet du module actuel est libéré.  Le gestionnaire d'événements est spécifié par un objet et son membre de pointeur\-vers\-une\-méthode.|  
|[Module::ReleaseNotifier, classe](../windows/module-releasenotifier-class.md)|Appelle un gestionnaire d'événements lorsque le dernier objet d'un module est libéré.|  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[Module::~Module, destructeur](../windows/module-tilde-module-destructor.md)|Libère l'instance actuelle de la classe Module.|  
  
### Constructeurs protégés  
  
|Name|Description|  
|----------|-----------------|  
|[Module::Module, constructeur](../windows/module-module-constructor.md)|Initialise une nouvelle instance de la classe Module.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[Module::Create, méthode](../windows/module-create-method.md)|Crée une instance de module.|  
|[Module::DecrementObjectCount, méthode](../windows/module-decrementobjectcount-method.md)|Décrémente le nombre d'objets suivis par le module.|  
|[Module::GetActivationFactory, méthode](../windows/module-getactivationfactory-method.md)|Obtient une fabrique d'activation pour le module.|  
|[Module::GetClassObject, méthode](../windows/module-getclassobject-method.md)|Récupère un cache de fabriques de classe.|  
|[Module::GetModule, méthode](../windows/module-getmodule-method.md)|Crée une instance de module.|  
|[Module::GetObjectCount, méthode](../windows/module-getobjectcount-method.md)|Retourne le nombre d'objets gérés par ce module.|  
|[Module::IncrementObjectCount, méthode](../windows/module-incrementobjectcount-method.md)|Incrémente le nombre d'objets suivis par le module.|  
|[Module::RegisterCOMObject, méthode](../windows/module-registercomobject-method.md)|Enregistre un ou plusieurs COM afin que les autres applications puissent se connecter à eux.|  
|[Module::RegisterObjects, méthode](../windows/module-registerobjects-method.md)|Enregistre COM ou les objets [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] afin que les autres applications puissent s'y connecter.|  
|[Module::RegisterWinRTObject, méthode](../windows/module-registerwinrtobject-method.md)|Enregistre un ou plusieurs objets [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] afin que les autres applications puisse s'y connecte.|  
|[Module::Terminate, méthode](../windows/module-terminate-method.md)|Provoque l'arrêt de toutes les fabriques instanciées par le module.|  
|[Module::UnregisterCOMObject, méthode](../windows/module-unregistercomobject-method.md)|Efface un ou plusieurs objets COM, empêchant d'autres applications de s'y connecter.|  
|[Module::UnregisterObjects, méthode](../windows/module-unregisterobjects-method.md)|Efface les objets dans le module spécifié afin que d'autres applications ne puissent pas s'y connecter.|  
|[Module::UnregisterWinRTObject, méthode](../windows/module-unregisterwinrtobject-method.md)|Efface un ou plusieurs objets [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] afin que d'autres applications ne puissent pas s'y connecter.|  
  
### Méthodes protégées  
  
|Name|Description|  
|----------|-----------------|  
|[Module::Create, méthode](../windows/module-create-method.md)|Crée une instance de module.|  
  
### Données membres protégées  
  
|Name|Description|  
|----------|-----------------|  
|[Module::objectCount\_, données de membre](../windows/module-objectcount-data-member.md)|Contient le nombre de classes créées avec la fonction [Make](../windows/make-function.md).|  
|[Module::releaseNotifier\_, données de membre](../windows/module-releasenotifier-data-member.md)|Contient un pointeur vers un objet ReleaseNotifier.|  
  
### Macros  
  
|||  
|-|-|  
|[ActivatableClass](../windows/activatableclass-macros.md)|Peuple un cache interne contenant une fabrique pouvant créer une instance de la classe spécifiée.  Cette macro spécifie les paramètres par défaut de fabrique et d'ID de groupe.|  
|[ActivatableClassWithFactory](../windows/activatableclass-macros.md)|Peuple un cache interne contenant une fabrique pouvant créer une instance de la classe spécifiée.  Cette macro vous permet de spécifier un paramètre de fabrique particulier.|  
|[ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md)|Peuple un cache interne contenant une fabrique pouvant créer une instance de la classe spécifiée.  Cette macro vous permet de spécifier des paramètres de fabrique et d'ID de groupe particuliers.|  
  
## Hiérarchie d'héritage  
 `ModuleBase`  
  
 `Module`  
  
 `Module`  
  
## Configuration requise  
 **En\-tête:** module.h  
  
 **Espace de noms:** Microsoft::WRL  
  
## Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)